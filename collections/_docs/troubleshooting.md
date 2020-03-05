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
    select astext(coverage) from omeka_neatline_records where astext(coverage) is null;

If these values exist, replace them with Point(0 0) using:

    update omeka_neatline_records set coverage=GeomFromText('POINT(0 0)') where astext(coverage) is null;
