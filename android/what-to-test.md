
## Testing Database

The recommended approach for testing your database implementation is writing a JUnit test that runs on an Android device and not on machine. 
Reason why it isn't recommended is because the version of SQLite running on your device—and your users' devices—might not match the version on your host machine. 
[Source](https://developer.android.com/training/data-storage/room/testing-db)
