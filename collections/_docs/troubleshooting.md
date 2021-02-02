---
layout: docs
title: Troubleshooting
---
# Troubleshooting

## Migrating to new versions of MySQL

Spatial data in MySQL can sometimes be quite fragile and it can also be difficult to determine what data is invalid or why it is invalid. Different versions of MySQL also implement more or less stringent checks for such values. Migrating MySQL versions will sometimes result in errors such as:

    Cannot get geometry object from data you send to the GEOMETRY field. 
 
One common case where these errors occur is upgrading from a pre-5.7 version of MySQL using null or empty geometry values in the coverage column in the omeka_neatline_records table, which does not allow null or empty values. Replacing these values with valid data (even placeholder, unmeaningful data such as "Point(0 0)") will get around this error.

Check whether this applies to your data by selecting for null astext(coverage) values:

    use {database name};
    select astext(coverage) from {database prefix}_neatline_records where astext(coverage) is null;

If these values exist, replace them with Point(0 0) using:

    update omeka_neatline_records set coverage=GeomFromText('POINT(0 0)') where astext(coverage) is null;

Additionally, there is a bug in Neatline that allows the creation of invalid polygons that contain fewer than the required 4 points. For example, "Polygon(0 0, 10 10, 0 0)" is not valid. MySQL did not invalidate these objects prior to version 5.6. Attempting to insert invalid geometry data into MySQL 5.6 produces a null value for the field. Doing so in MySQL 5.7 results in the same "Cannot get geometry object from data" error above. Use this query to select for invalid polygons:

    use {database name};
    select id, slug, title, astext(coverage) from {database prefix}_neatline_records where astext(coverage) regexp 'POLYGON([^,^)]*,){0,2}[^,^)]*\)';

To correct these erroneous polygons, either convert them to points or linestrings, circumvent the validation by repeating the closing point, or delete them altogether.