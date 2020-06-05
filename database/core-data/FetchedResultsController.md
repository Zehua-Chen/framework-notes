# Getting Objects

`var fetchedObjects` and `func object(at)` can be used to access fetched
objects.

- Not updated as the ordering changes

# User Initiated Editing

While handing user-initiated changes like re-ordering table, notifications from
fetched results controller needs to be ignored. To do this, use a boolean flag
which would be set to true at the beginning of user initiated changes, and set
to false in `controllerDidChangeContent`
