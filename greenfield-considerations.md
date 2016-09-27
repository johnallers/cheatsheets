* Assume large datasets. Always return paged results.
* How will it work at scale?
 * If tenant-based, what happens with 100s, 1000s of tenants.
* Store time values with timezone information and/or as UTC.
* Design with localization and internationalization in mind.
 * Consider return error codes from assemblies, instead of error messages.
