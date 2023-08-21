### V3 Set Quick Reply Messages

**JSON Fields Sent by App**:

| Field Name   | Field Type | Field Description                              |
| ------------ | ---------- | ---------------------------------------------- |
| version      | int        | Protocol version number, default 0 <br />Call message version number is 1 |
| num          | int        | Number of quick reply message details, maximum 10 |
| fast_items   | array      | Array of quick reply message details, containing msg_id and msg_data |

Each quick reply message detail contains the following fields:

| Field Name   | Field Type | Field Description                           |
| ------------ | ---------- | ------------------------------------------- |
| msg_id       | int        | Quick reply message ID, starting from 1     |
| msg_data     | char []    | Quick reply message content, maximum 68 bytes |

**Example**:

```json
{
  "version" : 0,
  "num" : 2,
  "fast_items" : [
    {
      "msg_id" : 1,
      "msg_data" : "Having meal, will contact later"
    },
    {
      "msg_id" : 2,
      "msg_data" : "Driving, will contact later"
    }
  ]
}
```

**JSON Fields Received by App**:

| Field Name   | Field Type | Field Description                           |
| ------------ | ---------- | ------------------------------------------- |
| is_success   | int        | 1: Success, 0: Failure                       |

**Example**:

```json
{
  "is_success" : 1
}
```