# SQLite Database in Android 📱🗄️

SQLite is a lightweight, embedded relational database management system widely used in Android applications to store and manage structured data locally on the device.

This project demonstrates how to use SQLite Database in Android for performing CRUD (Create, Read, Update, Delete) operations efficiently.

---

# 🚀 Features

✅ SQLite Database Integration  
✅ Local Data Storage  
✅ CRUD Operations  
✅ SQLiteOpenHelper Implementation  
✅ Database Schema Management  
✅ Android Studio Compatible  
✅ Beginner Friendly Example  

---

# 📚 Key Concepts

## Database
A structured collection of data organized into tables, rows, and columns.

## Table
Represents a single type of data entity consisting of rows and columns.

## Row
A single record within a table.

## Column
Represents a specific attribute or property of the data.

---

# 🛠 SQLite Operations

## Insert Data
Use:
```java
SQLiteDatabase.insert()
```

## Query Data
Use:
```java
SQLiteDatabase.query()
```

## Update Data
Use:
```java
SQLiteDatabase.update()
```

## Delete Data
Use:
```java
SQLiteDatabase.delete()
```

---

# 📂 Database Helper Example

```java
public class MyDatabaseHelper extends SQLiteOpenHelper {
    private static final String DATABASE_NAME = "my_app.db";
    private static final int DATABASE_VERSION = 1;

    public MyDatabaseHelper(Context context) {
        super(context, DATABASE_NAME, null, DATABASE_VERSION);
    }

    @Override
    public void onCreate(SQLiteDatabase db) {
        db.execSQL(UserContract.UserEntry.SQL_CREATE_TABLE);
    }

    @Override
    public void onUpgrade(SQLiteDatabase db, int oldVersion, int newVersion) {
        db.execSQL(UserContract.UserEntry.SQL_DELETE_TABLE);
        onCreate(db);
    }
}
```

---

# 📋 Database Schema Example

```java
public class UserContract {
    private UserContract() {}

    public static class UserEntry implements BaseColumns {
        public static final String TABLE_NAME = "users";
        public static final String COLUMN_NAME_USERNAME = "username";
        public static final String COLUMN_NAME_EMAIL = "email";

        public static final String SQL_CREATE_TABLE =
            "CREATE TABLE " + TABLE_NAME + " (" +
            _ID + " INTEGER PRIMARY KEY," +
            COLUMN_NAME_USERNAME + " TEXT," +
            COLUMN_NAME_EMAIL + " TEXT)";

        public static final String SQL_DELETE_TABLE =
            "DROP TABLE IF EXISTS " + TABLE_NAME;
    }
}
```

---

# 💾 Insert Example

```java
SQLiteDatabase db = myDatabaseHelper.getWritableDatabase();

ContentValues values = new ContentValues();
values.put(UserContract.UserEntry.COLUMN_NAME_USERNAME, "user123");
values.put(UserContract.UserEntry.COLUMN_NAME_EMAIL, "user@example.com");

long newRowId = db.insert(UserContract.UserEntry.TABLE_NAME, null, values);
```

---

# 🔍 Query Example

```java
String[] projection = {
    UserContract.UserEntry._ID,
    UserContract.UserEntry.COLUMN_NAME_USERNAME,
    UserContract.UserEntry.COLUMN_NAME_EMAIL
};

Cursor cursor = db.query(
    UserContract.UserEntry.TABLE_NAME,
    projection,
    null,
    null,
    null,
    null,
    null
);

cursor.close();
db.close();
```

---

# 🧑‍💻 Technologies Used

- Java
- Android SDK
- SQLite Database
- Android Studio

---

# 📱 Use Cases

- User Management Systems
- Offline Android Apps
- Notes Applications
- Student Management Apps
- Inventory Systems
- Local Data Storage
- Task Management Apps

---

# 👨‍💻 Developed By

## QuickCodeFix 🚀

### Connect With Me

- GitHub: https://github.com/vaibhavimore1811
- LinkedIn: https://linkedin.com/in/vaibhavi-more-9774a1196
- Instagram: https://instagram.com/quickcodefix

---

# ⭐ Support

If you found this project useful, give it a ⭐ on GitHub and share it with other Android developers.

---

# 📜 License

This project is open-source and free to use.
