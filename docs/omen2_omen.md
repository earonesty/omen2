# [omen2](omen2.md).omen
Simple object manager.


[(view source)](https://github.com/atakamallc/omen2/blob/master/omen2/omen.py)
## Omen(ABC)
Object relational manager: read and write objects from a db.


#### .__init__(self, db:notanorm.base.DbBase, module=None, type_checking=False, **table_types)
Create a new manager with a db connection.

#### .dump_dict(self) -> Dict[str, Iterable[Dict[str, Any]]]
Dump every table as a dictionary.

This just loops through all objects and calls _to_db on them.


#### .get_table_by_name(self, table_name)
Get table object by table name.

#### .load_dict(self, data_set:Dict[str, Iterable[Dict[str, Any]]])
Load every table from a dictionary.

#### .set_table(self, table:omen2.table.Table)
Set the table object associated with teh table type

#### .transaction(self)
Begin a database-wide transaction.

This will accumulate object modifications, adds and removes, and roll them back on exception.

It uses the underlying database's transaction mechanism.

On exception it will restore any cached information to the previous state.


