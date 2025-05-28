# mongodb_TODO
show dbs
admin    40.00 KiB
config  108.00 KiB
local    72.00 KiB
use minfydata
switched to db minfydata
db.moneyRecord.insertOne({})
{
  acknowledged: true,
  insertedId: ObjectId('6836cb3eef58176871db3456')
}
show collections
moneyRecord
db.moneyRecord.insertOne({name:"rahul"}{amount:"200"})
SyntaxError: Unexpected token, expected "," (1:39)

[0m[31m[1m>[22m[39m[90m 1 |[39m db[33m.[39mmoneyRecord[33m.[39minsertOne({name[33m:[39m[32m"rahul"[39m}{amount[33m:[39m[32m"200"[39m})
 [90m   |[39m                                        [31m[1m^[22m[39m[0m
db.moneyRecord.insertOne({name:"rahul"},{amount:"200"})
{
  acknowledged: true,
  insertedId: ObjectId('6836ccd0ef58176871db3457')
}
db.moneyRecord.find({"rahul"})
SyntaxError: Unexpected token (1:28)

[0m[31m[1m>[22m[39m[90m 1 |[39m db[33m.[39mmoneyRecord[33m.[39mfind({[32m"rahul"[39m})
 [90m   |[39m                             [31m[1m^[22m[39m[0m
db.moneyRecord.find({name:"rahul"})
{
  _id: ObjectId('6836ccd0ef58176871db3457'),
  name: 'rahul'
}
db.moneyRecord.find({amount:"200"})
db.moneyRecord.deleteOne({name:"rahul"})
{
  acknowledged: true,
  deletedCount: 1
}
db.moneyRecord.all({})
TypeError: db.moneyRecord.all is not a function
show collections
moneyRecord
use toDotask
switched to db toDotask
db.tasks.insertMany([
  { task: "Buy groceries", status: "pending", created_at: new Date() },
  { task: "Clean room", status: "completed", created_at: new Date() },
  { task: "Study MongoDB", status: "pending", created_at: new Date() }
])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('6836e3c7ef58176871db3458'),
    '1': ObjectId('6836e3c7ef58176871db3459'),
    '2': ObjectId('6836e3c7ef58176871db345a')
  }
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: 'pending',
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: 'completed',
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: 'pending',
  created_at: 2025-05-28T10:21:59.114Z
}
db.tasks.updateMany({status:"pending"},{$set:{status:false}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 2,
  modifiedCount: 2,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: 'completed',
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z
}
db.tasks.updateMany({status:"completed"},{$set:{status:true}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z
}
db.tasks.insertOne({task:"playing",created_at:new Date()})
{
  acknowledged: true,
  insertedId: ObjectId('6836ea88ef58176871db345b')
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z
}
db.tasks.updateMany(
  { status: { $exists: false } },
  { $set: { status: false } }
)
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: false
}
db.tasks.updateOne(
  { _id: ObjectId("6836e3c7ef58176871db345a") },
  { $set: { status: true } }
)
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
db.task.find()
db.task.find()
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: false
}
db.tasks.updateMany(
  { status: false },
  {
    $set: {
      status: true,
      update_time: new Date()
    }
  }
)
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 2,
  modifiedCount: 2,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z
}
db.tasks.insertOne({
  task: "New Task",
  status: false,
  created_at: new Date(),
  update_time: new Date()
})
{
  acknowledged: true,
  insertedId: ObjectId('6836ec02ef58176871db345c')
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: false,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z
}
db.tasks.updateOne({task:"New Task"},{$set :{status:true}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z
}
db.tasks.updateOne({task:"study mangoDB"},{$set:{status:false}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 0,
  modifiedCount: 0,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z
}
db.tasks.updateOne({task:"Study MangoDB"},{$set:{status:false}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 0,
  modifiedCount: 0,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z
}
db.tasks.updateOne({task:"Study MangoDB"},{$set:{status:false},{update_time:new Date()}})
SyntaxError: Unexpected token (1:63)

[0m[31m[1m>[22m[39m[90m 1 |[39m db[33m.[39mtasks[33m.[39mupdateOne({task[33m:[39m[32m"Study MangoDB"[39m}[33m,[39m{$set[33m:[39m{status[33m:[39m[36mfalse[39m}[33m,[39m{update_time[33m:[39m[36mnew[39m [33mDate[39m()}})
 [90m   |[39m                                                                [31m[1m^[22m[39m[0m
db.tasks.updateOne({task:"Study MangoDB"},{$set:{status:false,update_time:new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 0,
  modifiedCount: 0,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z
}
db.tasks.updateOne({_id: ObjectId("6836e3c7ef58176871db345a")},{$set:{status:false,update_time:new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T11:15:23.223Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z
}
db.tasks.countDocuments()
5
db.tasks.find.sort({})
TypeError: db.tasks.find.sort is not a function
db.tasks.sort()
TypeError: db.tasks.sort is not a function
db.tasks.find().sort({ status: -1 })
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T11:15:23.223Z
}
db.tasks.updateMany(
  {},
  { $set: { new_date: new Date() } }
)
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 5,
  modifiedCount: 5,
  upsertedCount: 0
}
db.tasks.updateMany(
  {},
  { $set: { new_date: new Date("2025-05-29T00:00:00Z") } }
)
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 5,
  modifiedCount: 5,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  new_date: 2025-05-29T00:00:00.000Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T11:15:23.223Z,
  new_date: 2025-05-29T00:00:00.000Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z,
  new_date: 2025-05-29T00:00:00.000Z
}
db.tasks.updateMany(
  {},
  { $set: { due_date: new Date("2025-05-29T00:00:00Z") } }
)

{
  acknowledged: true,
  insertedId: null,
  matchedCount: 5,
  modifiedCount: 5,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-29T00:00:00.000Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-29T00:00:00.000Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T11:15:23.223Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-29T00:00:00.000Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-29T00:00:00.000Z
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-29T00:00:00.000Z
}
db.tasks.updateMany(
  {},
  { $set: { due_date: new Date("2025-05-27T00:00:00Z") } }
)

{
  acknowledged: true,
  insertedId: null,
  matchedCount: 5,
  modifiedCount: 5,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T11:15:23.223Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z
}
db.tasks.find({
  dueDate: ISODate("2025-05-27T00:00:00Z")
});
db.tasks.find({
  dueDate: ISODate("2025-05-27T00:00:00Z")
});
db.tasks.find({
  due_date: ISODate("2025-05-27T00:00:00Z")
});
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T11:15:23.223Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z
}
db.tasks.updateMany(
  { priority: { $exists: false } },  // only update if priority doesn't exist
  { $set: { priority: "medium" } }
)
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 5,
  modifiedCount: 5,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T11:15:23.223Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
db.runCommand({
  collMod: "tasks",
  validator: {
    $jsonSchema: {
      bsonType: "object",
      properties: {
        priority: {
          enum: ["low", "medium", "high"],
          description: "priority must be one of: low, medium, high"
        }
      }
    }
  },
  validationLevel: "moderate"
})
{ ok: 1 }
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T11:15:23.223Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
db.tasks.updateOne(
  { task: "Buy groceries" },
  {
    $set: {
      status: false,
      updatedAt: new Date()
    }
  }
)
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium',
  updatedAt: 2025-05-28T14:30:29.435Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T11:15:23.223Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
db.tasks.updateOne(
  { task: "Buy groceries" },
  { $set: { due_date: new Date(Date.now() + 20 * 60000) } } 
)
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
db.tasks.find()
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-28T15:02:04.328Z,
  priority: 'medium',
  updatedAt: 2025-05-28T14:30:29.435Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T11:15:23.223Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
const now = new Date();
const twentyMinutesLater = new Date(Date.now() + 20 * 60 * 1000);

db.tasks.findOne({
  due_date: {
    $gte: now,
    $lte: twentyMinutesLater
  }
})
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-28T15:02:04.328Z,
  priority: 'medium',
  updatedAt: 2025-05-28T14:30:29.435Z
}
db.tasks.find().sort({ fieldName: 1 })
{
  _id: ObjectId('6836e3c7ef58176871db3458'),
  task: 'Buy groceries',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-28T15:02:04.328Z,
  priority: 'medium',
  updatedAt: 2025-05-28T14:30:29.435Z
}
{
  _id: ObjectId('6836e3c7ef58176871db3459'),
  task: 'Clean room',
  status: true,
  created_at: 2025-05-28T10:21:59.114Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836e3c7ef58176871db345a'),
  task: 'Study MongoDB',
  status: false,
  created_at: 2025-05-28T10:21:59.114Z,
  update_time: 2025-05-28T11:15:23.223Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836ea88ef58176871db345b'),
  task: 'playing',
  created_at: 2025-05-28T10:50:48.457Z,
  status: true,
  update_time: 2025-05-28T10:54:42.449Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
{
  _id: ObjectId('6836ec02ef58176871db345c'),
  task: 'New Task',
  status: true,
  created_at: 2025-05-28T10:57:06.802Z,
  update_time: 2025-05-28T10:57:06.802Z,
  new_date: 2025-05-29T00:00:00.000Z,
  due_date: 2025-05-27T00:00:00.000Z,
  priority: 'medium'
}
toDotask
Selection deleted
