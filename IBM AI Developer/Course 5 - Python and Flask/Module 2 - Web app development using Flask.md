[[Flask]]

Python libraries and frameworks

- Request library sends HTTP requests
- BeautifulSoup scrapes web pages
- SQLAlchemy is a SQL toolkit
- PyTest us a testing framework

Framework: Predefined structures for application development. Provides a set of guidelines for application development. Example: Django, Flask, and Web2Py

![[Pasted image 20261109230236.png]]

>[!tip] Important
>Framework enables you to build the complete application while libraries aid with specific functionality.

---
Introduction to Flask
[[flask]] #flask

- Flask is a micro web framework


![[Pasted image 20261110003053.png]]

![[Pasted image 20261110003131.png]]

![[Pasted image 20261110005315.png]]

![[Pasted image 20261110005356.png]]

![[Pasted image 20261110005438.png]]

---
Deploying web apps using flask

![[Pasted image 20261110234815.png]]

![[Pasted image 20261110234850.png]]

---

# Decorators in Flask

Estimated time needed: **10** minutes

## Objectives

After reading this page, you will be able to:

1. Understand what are decorators
2. Understand the two kind of decorators you come across in a python application.
3. When and how to use the decorators.

### What are decorators

Decorators are functions that modify or extend the behavior of another function or class without modifying its source code.

## Method decorators

Let's say we have a python code where we want all the output to be in JSON format. It doesn't make sense to include code for these in each of the methods as it makes the lines of code redundant. In such cases, we can handle this with a decorator.

python

```python
def jsonify_decorator(function):
    def modifyOutput():
        return {"output":function()}
    return modifyOutput

@jsonify_decorator
def hello():
    return 'hello world'

@jsonify_decorator
def add():
    num1 = input("Enter a number - ")
    num2 = input("Enter another number - ")
    return int(num1)+int(num2)

print(hello())
print(add())
```

A decorator is a function that modifies or extends the behavior of another function. A wrapper function is commonly used inside a decorator to add that behavior. In the above code sample, `jsonify-decorator` is the decorator method. We have added this decorator to `hello()` and `add()`. The output of these method calls will now be wrapped and decorated with the jsonify_decorator.

The output of invoking the above python code will be:

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0222EN-SkillsNetwork/labs/module_1/images/decorated_output.png)

As you can see the method call has been wrapped with the decorator. The coder has a free will to choose the name of the decorator. Here the name chosen is `jsonify_decorator`.

## Route Decorators

You may have observed when you visit any domain you have the root and then have other end-points you can access. See the examples below.

`https://mydomain.com/`

`https://mydomain.com/about`

`https://mydomain.com/register`

We will look at creating these endpoints when we will create a web application using the flask module in the labs that will follow.

But to define these endpoints in Python we use what we call **Route Decorators**.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0222EN-SkillsNetwork/labs/module_1/images/route_decorator.png)

**@app.route("/")** is a Python decorator that Flask provides to assign URLs in our app to functions easily. You can easily tell that the decorator is telling our @app that whenever a user visits our application's domain, in our case, execute the `home()` function.

We can handle multiple routes with a single function by just stacking additional route decorators above the method which should be invoked when the route is called. The following is a valid example of serving the same "Hello World!" message for 3 separate routes:

ruby

```
@app.route("/")
@app.route("/home")
@app.route("/index")
def home():
    return "Hello World!"
```

The `route()` decorator accepts a `methods` parameter, which can be used to specify the HTTP methods supported by the route. We will learn about this in the later sections.

The route decorator can also be more specific. For example, to get the details of a user whose userId is U0001, you may go to `http://mydomain.com/userdetails/U0001`. It doesn't make sense to define a different route for each user you may be dealing with. In such cases, we define the route like this.

ruby

```
@app.route("/userdetails/<userid>")
def getUserDetails(userid):
    return "User Details for  "+userid
```

---
Flask basic Applications and Routes

 ![[Pasted image 20261111002256.png]]

---
Request and Response Objects

![[Pasted image 20261112001511.png]]

![[Pasted image 20261112001648.png]]

![[Pasted image 20261112001814.png]]

---
Dynamic Routes

![[Pasted image 20261112002016.png]]

![[Pasted image 20261112002049.png]]

![[Pasted image 20261112002149.png]]

---
Error Handling