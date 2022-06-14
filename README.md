# gov_central
CENTRALISED PERMITS CERTIFICATE and LICENSES SERVICE
We have used DevOps tools.
--Docker
---install docker for desktop on your local machine
---go to dockerhub.com and pull docker image
------image name is   omang/bots_gov
-----run the image on your local machine.

--bots_gov is centralised permits, certificate licenses backend/micro -service
----we expose the micro-service services through RESTFUL apis using Expressjs on top of node.
----nodejs is used as a server
----Mongodb is used as a database.

---using a service
-----download and install any api test app..we recommend postman.

---exposed api's
----client api's
----------register user
------------------localhost:4200/api/auth/register   method:POST    test_data: {
    "username":"nchimaxy",
    "fname":"omanag",
    "lname":"ramoswaane",
    "email":"lmoswaane@gmail.com",
    "phonenumber":"173725320",
    "password":"1234567"
}
------------------it return the above object with an object id

---------login user
-------------------localhost:4200/api/auth/login   method:POST  test_data: {"username":"nchimaxy", "password":"1234567"}
------------------------it return an object with and objectid which we will use as we move on.
----------get user dashboard
-------------------localhost:4200/api/dashboard/getyours  method:POST test_data: {"user_id":"the return objectid from login returned object"}

---------create a ministry , ministry location and authorised person to handle permit, certificate, license applications.
--------------------localhost:4200/api/ministry/add/access method:POST test_data:{
    "ministry_name":"labor and home affiars",
    "location": "gantsi",
    "fname":"victor",
    "access_key": "12345"
}
--------login created ministry
---------------------localhost:4200/api/ministry/get/access method:POST test_data:{"access_key":"12345"}

--------permit application process(a client processes an apllication)
---------------------localhost:4200/api/permit/create   method:POST test_data:{
    "user_id": "62a870460d110f875b4d536d",
    "permit_type": "farming permit",
    "permit_number": "001",
    "ministry": "labour",
    "location": "gantsi",
    "approved": false
}

------------ministry approves an application
------------------localhost:4200/api/ministry/approve/application method:POST test_data:{
    "app_id":"62a8985f93bcd896f8284cef"
}
SAME FUNCTINALITY FOR CERTIFICATE, LICENSE PROCESSING SO WE ONLY DID THE PERMIT MIN-MICRO-SERVIVE FUNCTINALITY DUE TO LIMITED TIME WE WERE GIVEN.
--------ENJOY-------ENJOY------THANKS-------










