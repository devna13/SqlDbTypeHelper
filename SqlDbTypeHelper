
    public static class SqlDbTypeHelper
    {
        // See:  https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql-server-data-type-mappings
        // DbType to SqlDbType 
        public static readonly Dictionary<DbType, SqlDbType> DbTypeToSqlDbTypes = new Dictionary<DbType, SqlDbType> {
            { DbType.Int64 , SqlDbType.BigInt},
            { DbType.Binary , SqlDbType.VarBinary },
            { DbType.Boolean , SqlDbType.Bit },
            { DbType.AnsiStringFixedLength  , SqlDbType.Char },
            { DbType.Date , SqlDbType.Date },
            { DbType.DateTime , SqlDbType.DateTime },
            { DbType.DateTime2 , SqlDbType.DateTime2 },
            { DbType.DateTimeOffset , SqlDbType.DateTimeOffset },
            { DbType.Decimal , SqlDbType.Decimal },
            { DbType.Double , SqlDbType.Float },
            { DbType.Int32 , SqlDbType.Int },
            { DbType.StringFixedLength , SqlDbType.NChar },
            { DbType.String , SqlDbType.NVarChar },
            { DbType.Single , SqlDbType.Real },
            { DbType.Int16 , SqlDbType.SmallInt },
            { DbType.Object , SqlDbType.Variant },
            { DbType.Time , SqlDbType.Time },
            { DbType.Byte , SqlDbType.TinyInt },
            { DbType.Guid , SqlDbType.UniqueIdentifier },
            { DbType.AnsiString, SqlDbType.VarChar },
            { DbType.Xml , SqlDbType.Xml },
            //{ DbType.Binary , SqlDbType.Binary },
            //{ DbType.Binary , SqlDbType.Timestamp },
            //{ DbType.DateTime , SqlDbType.DateTime },
            //{ DbType.Decimal , SqlDbType.SmallMoney },
            //{ DbType.Decimal , SqlDbType.Money },
            //{ DbType.String , SqlDbType.Text },
            //{ DbType.String , SqlDbType.NText },
            //{ DbType.Binary , SqlDbType.Timestamp },
        };

        // SqlDbType to DbType  
        public static readonly Dictionary<SqlDbType, DbType> SqlDbTypeToDbType = new Dictionary<SqlDbType, DbType>
        {
            { SqlDbType.BigInt , DbType.Int64 },
            { SqlDbType.VarBinary , DbType.Binary},
            { SqlDbType.Bit , DbType.Boolean },
            { SqlDbType.Char , DbType.AnsiStringFixedLength },
            { SqlDbType.Date , DbType.Date },
            { SqlDbType.DateTime , DbType.DateTime },
            { SqlDbType.DateTime2 , DbType.DateTime2 },
            { SqlDbType.DateTimeOffset , DbType.DateTimeOffset },
            { SqlDbType.Decimal , DbType.Decimal },
            { SqlDbType.Float , DbType.Double },
            { SqlDbType.Binary , DbType.Binary },
            { SqlDbType.Int , DbType.Int32 },
            { SqlDbType.Money , DbType.Decimal },
            { SqlDbType.NChar , DbType.StringFixedLength },
            { SqlDbType.NText , DbType.String },
            { SqlDbType.NVarChar , DbType.String },
            { SqlDbType.Real , DbType.Single },
            { SqlDbType.SmallInt , DbType.Int16 },
            { SqlDbType.SmallMoney , DbType.Decimal },
            { SqlDbType.Variant , DbType.Object },
            { SqlDbType.Text , DbType.String },
            { SqlDbType.Time , DbType.Time },
            { SqlDbType.TinyInt , DbType.Byte },
            { SqlDbType.UniqueIdentifier , DbType.Guid },
            { SqlDbType.VarChar , DbType.AnsiString },
            { SqlDbType.Xml , DbType.Xml },
            { SqlDbType.Timestamp , DbType.Binary },
        };

        /// <summary>
        /// Returns null or matching SqlDbType
        /// </summary>
        public static SqlDbType ToSqlDbType(this DbType dbType)
        {
            var result = SqlDbType.VarChar;
            return DbTypeToSqlDbTypes.TryGetValue(dbType, out result) ? result : result;
        }

        /// <summary>
        /// Returns null or matching DbType
        /// </summary>
        public static DbType ToDbType(this SqlDbType sqlDbType)
        {
            DbType result;
            return SqlDbTypeToDbType.TryGetValue(sqlDbType, out result) ? result : result;
        }

        /// <summary>
        /// If no match found, returns SqlDbType.VarChar
        /// </summary>
        public static SqlDbType ToSqlDbTypeSafe(this DbType dbType)
        {
            SqlDbType result = SqlDbType.VarChar;
            if (DbTypeToSqlDbTypes.TryGetValue(dbType, out result))
                return result;
            return result;
        }

        /// <summary>
        /// If no match found, returns DbType.String
        /// </summary>
        public static DbType ToDbTypeSafe(this SqlDbType sqlDbType)
        {
            DbType result = DbType.String;
            if (SqlDbTypeToDbType.TryGetValue(sqlDbType, out result))
                return result;
            return result;
        }
    }
