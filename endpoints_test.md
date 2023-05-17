3) Call our endpoints - Here are the requests we can make to our new endpoints.

> This retrieves the auth token for malcolm

curl -X POST -F 'username=malcolm' -F 'password=password' http://api:8000/api-token-auth/

http post http://api:8000/api-token-auth/ username=malcolm password=password


> This will retrieve all items

curl -X GET -H 'Authorization: Token 71618355ed3ea4d6d27bbbd9f756317bc4e8bc5c' http://api:8000/item/

http http://api:8000/item/ 'Authorization: Token 71618355ed3ea4d6d27bbbd9f756317bc4e8bc5c'


> This will retreive a single item

curl -X GET -H 'Authorization: Token 71618355ed3ea4d6d27bbbd9f756317bc4e8bc5c' http://api:8000/item/784185f9-0b11-47c1-ab4a-baf02b4944dc/

http http://api:8000/item/784185f9-0b11-47c1-ab4a-baf02b4944dc/ 'Authorization: Token 71618355ed3ea4d6d27bbbd9f756317bc4e8bc5c' 

> This retrieve all orders

curl -X GET -H 'Authorization: Token 71618355ed3ea4d6d27bbbd9f756317bc4e8bc5c' http://api:8000/order/

http http://api:8000/order/ 'Authorization: Token 71618355ed3ea4d6d27bbbd9f756317bc4e8bc5c'

> This will place an order for item id = 784185f9-0b11-47c1-ab4a-baf02b4944dc quantity = 1

curl -X POST -H 'Content-Type: application/json' -H 'Authorization: Token 71618355ed3ea4d6d27bbbd9f756317bc4e8bc5c' -d '{"item": "784185f9-0b11-47c1-ab4a-baf02b4944dc", "quantity": "1"}' http://api:8000/order/

http http://api:8000/order/ 'Authorization: Token 71618355ed3ea4d6d27bbbd9f756317bc4e8bc5c' item="784185f9-0b11-47c1-ab4a-baf02b4944dc" quantity="1"


> This get order id = 	f378151b-e246-485a-a70d-4f7089ddbe5c

curl -X GET -H 'Authorization: Token 71618355ed3ea4d6d27bbbd9f756317bc4e8bc5c' http://api:8000/order/	f378151b-e246-485a-a70d-4f7089ddbe5c/

http http://api:8000/order/	f378151b-e246-485a-a70d-4f7089ddbe5c/ 'Authorization: Token 71618355ed3ea4d6d27bbbd9f756317bc4e8bc5c'

> This will create a contact request

curl -X POST -H "Content-type: application/json" -d '{"name": "Bobby Stearman", "message": "test", "email":"bobby@didcoding.com"}' 'http://api:8000/contact/'

http http://api:8000/contact/ name="Bobby Stearman" message="test" email="bobby@didcoding.com"