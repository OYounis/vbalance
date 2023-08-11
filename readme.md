# vBalance
`vBalance` is a `csh script` that handles employee leave requests in a company
------------------------------------------------------------

## Commands

| Command       |    Function                                 |  Note |
|---------------|---------------------------------------------|-------|
| help          | Print help message                          |       |
| add-record    | Add new employee to the record              |       |
| rem-record    | Remove employee record                      |       |
| my-record     | Display current employee record             |       |
| request-leave | Send leave request (annual - sick - unpaid) |       |
| print-record  | Display entire company record               |       |
| vacations     | Display public holidays                     |       |
| quit          | Quit the program                            |       |
------------------------------------------------------------

## Test Plan

| Feature / Command |    Action / Scenario                                           | Expected Action         |
|-------------------|----------------------------------------------------------------|:-----------------------:|
| help              | Print help message                                             | Help message printed    |
|                   | Add new employee record                                        | Employee record added   |
|                   | First name contains alpanumericals                             | Error                   |
| add-record        | Last name contains alpanumericals                              | Error                   |
|                   | ID contains special charachters and/or less than 5 digits      | Error                   |
|                   | ID Already exisits in record                                   | Error                   | 
| rem-record        | Remove record                                                  | Employee record removed |
| my-record         | Display record                                                 | Employee record displayed|
|                   | Request annual/sick leave that does not exceed the balance     | Leave Accepted      |
|                   | Request annual/sick leave that exceeds the balance             | Leave Denied |
| request-leave     | Request unpaid leave no more than 3 days                       | Leave Accepted |
|                   | Extending an unpaid leave that accumulates to 3 days or less   | Leave Accepted |
|                   | Extending an unpaid leave that accumulated to more than 3 days | Leave Denied |
|                   | Request leave that intersect with holidays and/or weekends     | Only work days should be subtracted from the balance |
| print-record      | Print record                                                   | Company record displayed       |
| vacations         | print vacations                                                | Holidays displayed      |
| quit              | Quit the program                                               | Program Exit       |

``` 
Requesting a leave that exceeds the current year and goeas into the next year has not been tested. It is expected to be accepted if enough balance is available.
```

``` 
Requesting a leave that overlaps with another leave will still count the overlapping days as new leave days and subtract them from the balance again
```