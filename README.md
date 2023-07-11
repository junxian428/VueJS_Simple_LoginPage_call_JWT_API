# loginpage


POST request (register)

http://localhost:8086/api/v1/auth/register


{

    "email": "junxian428@gmail.com",

    "password": "junxian428"

}


______________________________________________________________

use jwt;

UPDATE _user
SET role = 'USER'
WHERE id = 52;

select * from _user