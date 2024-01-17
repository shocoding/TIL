```
number_of_people = 0
number_of_book = 100

def increase_user():
    global number_of_people
    number_of_people += 1

def decrease_book(number = int):
    global number_of_book
    number_of_book = number_of_book - number
    print(f'남은 책의 수 : {number_of_book}')

def create_user(name, age, address):
    increase_user()
    user_info = {'name' : name, 'age' : age, 'address' : address}
    result = user_info['name']
    print(f'{result}님 환영합니다!')
    return user_info

def rental_book(info):
    decrease_book(info['age']//10)
    print(f'{info["name"]}님이 {info["age"]//10}권의 책을 대여하였습니다.')
    
name = ['김시습', '허균', '남영로', '임제', '박지원']
age = [20, 16, 52, 36, 60]
address = ['서울', '강릉', '조선', '나주', '한성부']

many_user = list(map(create_user, name, age, address))
#print(many_user)
info = list(map(lambda x: {'name' : x['name'], 'age' : x['age']}, many_user))
#print(info)
list(map(rental_book, info))
```

map(함수, 매개변수)
매개변수를 함수 안에 계속 넣어줌.
for문 이랑 비슷함

(lambda 매개변수: 함수, 매개변수에 넣을 값)
매개변수에 넣을 값을 매개변수에 넣고 함수에 넣어줌.
