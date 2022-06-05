# get-value-from-nested-dic

We have a nested object, we would like a function that you pass in the object and a key and get back the value. How this is implemented is up to you.

Example Inputs:

object = {“a”:{“b”:{“c”:”d”}}}
key = a/b/c

object = {“x”:{“y”:{“z”:”a”}}}
key = x/y/z
value = a
def get_value(obj, key):
    
    '''function takes in a nested dictionary object and a key to return the corresponding value. 
    note: Key needs to be passed as a string'''
    
    value = obj
       
    for k in key.split('/'):
        value = value[k]
        
    return value
#test cases


test_obj_1 = {'a':{'b':{'c':'d'}}}
key_1 = 'a/b/c'

test_obj_2 = {'x':{'y':{'z':'a'}}}
key_2 = 'x/y/z'

test_obj_3 = {'a':{'b':{'c':{'x':{'y':{'z':{'a':{'b':{'c':420}}}}}}}}}
key_3 = 'a/b/c/x/y/z/a/b/c'


result = []
for obj, key in [(test_obj_1,key_1), (test_obj_2,key_2), (test_obj_3,key_3)]:
    
    result.append(get_value(obj, key))
print(f'Test \t\t o/p \t\t expected o/p \n\ntest_1 \t\t {result[0]}\t\t d \ntest_2 \t\t {result[1]}\t\t a \ntest_3 \t\t {result[2]}\t\t 420 ')
Test 		 o/p 		 expected o/p 

test_1 		 d		 d 
test_2 		 a		 a 
test_3 		 420		 420 
