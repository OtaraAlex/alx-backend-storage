# NoSQL

## Resources

* [NoSQL Databases Explained](https://riak.com/resources/nosql-databases/)
* [What is NoSQL ?](https://www.youtube.com/watch?v=qUV2j3XBRHc&ab_channel=Guru99)
* [MongoDB with Python Crash Course - Tutorial for Beginners](https://www.youtube.com/watch?v=E-1xI85Zog8)
* [MongoDB Tutorial 2 : Insert, Update, Remove, Query](https://www.youtube.com/watch?v=CB9G5Dvv-EE&ab_channel=DerekBanas)
* [Aggregation](https://www.mongodb.com/docs/manual/aggregation/)
* [Introduction to MongoDB and Python](https://realpython.com/introduction-to-mongodb-and-python/)
* [mongo Shell Methods](https://www.mongodb.com/docs/manual/reference/method/)
* [The mongo Shell](https://www.mongodb.com/docs/manual/program/mongod/)

## Objectives

* What NoSQL means
* What is difference between SQL and NoSQL
* What is ACID
* What is a document storage
* What are NoSQL types* 
* What are benefits of a NoSQL database
* How to query information from a NoSQL database
* How to insert/update/delete information from a NoSQL database
* How to use MongoDB

## Tasks

* [0-list_databases](./0-list_databases)
A script that lists all databases in MongoDB.

* [1-use_or_create_database](./1-use_or_create_database)
A script that creates or uses the database `my_db`

* [2-insert](./2-insert)
A script that inserts a document in the collection `school`:
  * The document must have one attribute `name` with value “Holberton school”
  * The database name will be passed as option of `mongo` command

* [3-all](./3-all)
A script that lists all documents in the collection `school`:
  * The database name will be passed as option of `mongo` command

* [4-match](./4-match)
A script that lists all documents with `name="Holberton school"` in the collection `school`:
  * The database name will be passed as option of `mongo` command

* [5-count](./5-count)
A script that displays the number of documents in the collection `school`:
  * The database name will be passed as option of `mongo` command

* [6-update](./6-update)
A script that adds a new attribute to a document in the collection `school`:
  * The script should update only document with `name="Holberton school"` (all of them)
  * The update should add the attribute `address` with the value “972 Mission street”
  * The database name will be passed as option of `mongo` command

* [7-delete](./7-delete)
A script that deletes all documents with `name="Holberton school"` in the collection `school`:
  * The database name will be passed as option of `mongo` command

* [8-all.py](./8-all.py)
A Python function that lists all documents in a collection:
  * Prototype: `def list_all(mongo_collection)`:
  * Return an empty list if no document in the collection
  * `mongo_collection` will be the `pymongo` collection object

* [9-insert_school.py](./9-insert_school.py)
A Python function that inserts a new document in a collection based on `kwargs`:
  * Prototype: `def insert_school(mongo_collection, **kwargs)`:
  * `mongo_collection` will be the `pymongo` collection object
  * Returns the new `_id`

* [10-update_topics.py](./10-update_topics.py)
A Python function that changes all topics of a school document based on the name:
  * Prototype: `def update_topics(mongo_collection, name, topics)`:
  * `mongo_collection` will be the `pymongo` collection object
  * `name` (string) will be the school name to update
  * `topics` (list of strings) will be the list of topics approached in the school

* [11-schools_by_topic.py](./11-schools_by_topic.py)
A Python function that returns the list of school having a specific topic:
  * Prototype: `def schools_by_topic(mongo_collection, topic)`:
  * `mongo_collection` will be the `pymongo` collection object
  * `topic` (string) will be topic searched

* [12-log_stats.py](./12-log_stats.py)
A Python script that provides some stats about Nginx logs stored in MongoDB:
  * Database: `logs`
  * Collection: `nginx`
  * Display (same as the example):
      - first line: `x logs` where `x` is the number of documents in this collection
      - second line: `Methods`:
      - 5 lines with the number of documents with the `method = ["GET", "POST", "PUT", "PATCH", "DELETE"]` in this order (see example below - warning: it’s a tabulation before each line)
      - one line with the number of documents with:
        * `method=GET`
        * `path=/status`
You can use this dump as data sample: [dump.zip](https://github.com/OtaraAlex/alx-backend-storage/issues/1#issue-1809499810)

The output of your script **must be exactly the same as the example**
```
guillaume@ubuntu:~/0x01$ curl -o dump.zip -s "https://s3.amazonaws.com/intranet-projects-files/holbertonschool-webstack/411/dump.zip"
guillaume@ubuntu:~/0x01$ 
guillaume@ubuntu:~/0x01$ unzip dump.zip
Archive:  dump.zip
   creating: dump/
   creating: dump/logs/
  inflating: dump/logs/nginx.metadata.json  
  inflating: dump/logs/nginx.bson    
guillaume@ubuntu:~/0x01$ 
guillaume@ubuntu:~/0x01$ mongorestore dump
2018-02-23T20:12:37.807+0000    preparing collections to restore from
2018-02-23T20:12:37.816+0000    reading metadata for logs.nginx from dump/logs/nginx.metadata.json
2018-02-23T20:12:37.825+0000    restoring logs.nginx from dump/logs/nginx.bson
2018-02-23T20:12:40.804+0000    [##......................]  logs.nginx  1.21MB/13.4MB  (9.0%)
2018-02-23T20:12:43.803+0000    [#####...................]  logs.nginx  2.88MB/13.4MB  (21.4%)
2018-02-23T20:12:46.803+0000    [#######.................]  logs.nginx  4.22MB/13.4MB  (31.4%)
2018-02-23T20:12:49.803+0000    [##########..............]  logs.nginx  5.73MB/13.4MB  (42.7%)
2018-02-23T20:12:52.803+0000    [############............]  logs.nginx  7.23MB/13.4MB  (53.8%)
2018-02-23T20:12:55.803+0000    [###############.........]  logs.nginx  8.53MB/13.4MB  (63.5%)
2018-02-23T20:12:58.803+0000    [#################.......]  logs.nginx  10.1MB/13.4MB  (74.9%)
2018-02-23T20:13:01.803+0000    [####################....]  logs.nginx  11.3MB/13.4MB  (83.9%)
2018-02-23T20:13:04.803+0000    [######################..]  logs.nginx  12.8MB/13.4MB  (94.9%)
2018-02-23T20:13:06.228+0000    [########################]  logs.nginx  13.4MB/13.4MB  (100.0%)
2018-02-23T20:13:06.230+0000    no indexes to restore
2018-02-23T20:13:06.231+0000    finished restoring logs.nginx (94778 documents)
2018-02-23T20:13:06.232+0000    done
guillaume@ubuntu:~/0x01$ 
guillaume@ubuntu:~/0x01$ ./12-log_stats.py 
94778 logs
Methods:
    method GET: 93842
    method POST: 229
    method PUT: 0
    method PATCH: 0
    method DELETE: 0
47415 status check
guillaume@ubuntu:~/0x01$ 
```

* [100-find](./100-find)
A script that lists all documents with `name` starting by `Holberton` in the collection `school`:
  * The database name will be passed as option of `mongo` command

* [101-students.py](./101-students.py)
A Python function that returns all students sorted by average score:
  * Prototype: `def top_students(mongo_collection)`:
  * `mongo_collection` will be the `pymongo` collection object
  * The top must be ordered
  * The average score must be part of each item returns with key = `averageScore`

* [102-log_stats.py](./102-log_stats.py)
Improve `12-log_stats.py` by adding the top 10 of the most present IPs in the collection `nginx` of the database `logs`:
  * The IPs top must be sorted (like the example below)

```
guillaume@ubuntu:~/0x01$ ./102-log_stats.py 
94778 logs
Methods:
    method GET: 93842
    method POST: 229
    method PUT: 0
    method PATCH: 0
    method DELETE: 0
47415 status check
IPs:
    172.31.63.67: 15805
    172.31.2.14: 15805
    172.31.29.194: 15805
    69.162.124.230: 529
    64.124.26.109: 408
    64.62.224.29: 217
    34.207.121.61: 183
    47.88.100.4: 166
    45.249.84.250: 160
    216.244.66.228: 150
```