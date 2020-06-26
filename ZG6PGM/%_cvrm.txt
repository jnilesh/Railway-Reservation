TYPE-POOL VRM .

TYPES:
*-- Single Value in Value Set
       BEGIN OF VRM_VALUE,
         KEY(40) TYPE C,
         TEXT(80) TYPE C,
       END OF VRM_VALUE,
*-- Table of Values
       VRM_VALUES TYPE VRM_VALUE OCCURS 0,
*-- Id of Value Set
       VRM_ID TYPE VRM_VALUE-TEXT,
*-- table of Ids of Value Set
       VRM_IDS TYPE VRM_ID OCCURS 0,
*-- QueueRow
       BEGIN OF VRM_QUEUEROW,
         TAG,
         VALUE TYPE VRM_VALUE,
       END   OF VRM_QUEUEROW,
*-- Queue
       VRM_QUEUE TYPE VRM_QUEUEROW OCCURS 0.

CONSTANTS:
  VRM_TYPE(20)                          VALUE 'application',
  VRM_SUBTYPE(20)                       VALUE 'x-sapvaluesets',
  VRM_QUEUE_TAG_HEADER                  VALUE 'T',
  VRM_QUEUE_TAG_SUBHEADER               VALUE 'X',
  VRM_QUEUE_TAG_ENTRY                   VALUE ' ',
  VRM_QUEUE_KEY_TYPE TYPE VRM_VALUE-KEY VALUE 'TYPE',
  VRM_QUEUE_KEY_NAME TYPE VRM_VALUE-KEY VALUE 'NAME'.
