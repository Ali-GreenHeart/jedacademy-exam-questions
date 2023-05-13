<style>
    *{
        font-size: 20px;
    }
</style>

## <center><b> _Requirements of Final Project of Node01 group._</b></center>

# <center> `Hotel Management Website` </center>

Welcome to our final project guys! It's been great pleasure to trip into JS
world! For final project, you need to create backend application (RESTful APIs )
for Hotel Management System, where users can reserve rooms for their holidays.
Before diving into requirements, here are the few tips:

1. API structure must be like this: _`http://localhost:5050/api`_
2. Differ admin routes from user routes.
3. Providing documentation is optional (swagger)

So, let's describe the requirements, itself:

## 1. `Collections` (schemas)

a. `Users` : firstName[_string_], lastName[_string_], email[_string_],
phoneNumber[string], password[_string_], role[_'user', 'admin'_]

b. `Rooms` : roomNumber[_number_], roomType[_string_],occupancy[_number_],
price[_number_], availability[_boolean_], isActive[boolean]

c. `Reservations`: userId[ObjectId], roomNumber[_number_], checkInDate[_Date_],
checkOutDate[_Date_], totalAmount[_number_], isActive[boolean]

## 2. User Authentication and Authorization

    The website should have a secure authentication and authorization system for users accessing the system. The users should be able to register, log in. Reservation can only happen after signed-in process. By the way, use JWT token for both roles and sessions.
    Full routes: 
    signin: https://localhost:5050/api/sign-in
    signup: https://localhost:5050/api/sign-up

## 3. Room Management

    The website should have a module to manage rooms, including the ability to create, update, and delete rooms. Only, admin should do it! So, please, provide it on other route, called, `/admin/room`. Rooms' properties were given on schema.
    Full routes : 
    1. for users:
    get all rooms: https://localhost:5050/api/room
    get room by id: https://localhost:5050/api/room/:id
    get all avaiable rooms: https://localhost:5050/api/avaiableRooms

    2. for admins
    create room: https://localhost:5050/api/admin/room
    update room: https://localhost:5050/api/admin/room/:id
    delete room: https://localhost:5050/api/admin/room/:id  [isActive-i false et]

## Reservation Management

    The most logical part of the application is reservation process. We need this module to manage reservations, including the ability to create, edit, and cancel reservations.
    Full routes:
    reserve a room [post]: https://localhost:5050/api/admin/reserveRoom
    {userId, roomNumber, checkInDate,checkOutDate, }
    filter: checkOutDate < checkInDate2

    cancel a reserve: https://localhost:5050/api/admin/cancelReserve/:roomNumber
    get reserved rooms: https://localhost:5050/api/admin/reservedRooms
    {checkInDate, checkOutDate}
    make room available[put]: https://localhost:5050/api/admin/makeRoomAvailable/:roomNumber

<!--
        1. RESERVE EDILMIS OTAQ NECE BOSALIR!
        12-15.03 otaq rezerv edilib. ayin 16si otaq bosdur. availlable true

        12-15.03    16.03

        Fevral: 28 eded reservation setir:


https://www.youtube.com/watch?v=ExsYLyv7-zQ


-->
