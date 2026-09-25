1. When POST /devices with probe body was posted twice, a status code of 201 Created was produced. When GET /devices was ran, a status code of 200 OK was produced. The probe body was added to the listing twice, carrying the number of devices up from 5 to 7.

2. When PUT /devices/attic with the attic body was posted twice, a statutus code of 200 OK was produced. When GET /devices was ran, a status code of 200 OK was produced and the room and temp aspects of the attic body was updated. 

3. When DELETE /devices/fridge was done twice, a 404 Not Found status code was produced with the detail "No device found" When GET /devices was ran, a 200 OK status code was produced, only 6 devices were listed and fridge was not there.

The POST and PUT methods left the system in the same state whether the request once or twice, and the DELETE did not. This property is called Idempotency and the DELETE method can be idempotent but only after the method is done one time already.
