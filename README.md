## Ex.05 Design a Website for Server Side Processing
## Date: 06/10/2025

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :    math.html
```
<html> 
<head> 
<title>BMI</title> 
<style>
        body{
          background-color: rgb(89, 67, 233);
          border-top: 20;
        }
        .m{
          background-color:rgb(225, 44, 242);
          border-style: dotted;
          margin-top: 150px;
          margin-left: 500px;
          margin-right: 500px;
          
        }
            .main{
                font-size: 250%;
                text-align: center;
                background-color: rgb(167, 21, 230);
                 margin-left: 50px;
                  margin-right: 50px;
                  padding: 50px;
                  
                  
            }
            .a{
                font-size: 150%;
                text-align: center;
                background-color: rgb(52, 33, 62);
                 margin-left: 50px;
                  margin-right: 50px;
                
                 
            }
            form{
              text-align: center;
              background-color: rgb(188, 50, 195);
               margin-left: 50px;
             margin-right: 50px;
             padding: 50px;
            }
           
        </style>
</head> 

    <center>
    <h1>HEMA PRIYA S(25017270)</h1>
<div class="edge"> 
<div class="box"> 
<h1>BMI</h1> 
<form method="POST">
{%csrf_token %}
<div class="formelt"> 
height:<input type="text" name="height" value="{{h}}"></input>(in m)<br/> 
</div> 
<div class="formelt"> 
weight:<input type="text" name="weight" value="{{w}}"></input>(in kg)<br/> 
</div> 
<div class="formelt"> 
<input type="submit" value="Calculate"></input><br/> 
</div> 
<div class="formelt"> 
BMI:<input type="text" name="BMI" value="{{BMI}}"></input>kg/m<sup>2</sup><br/> 
</div>
</form>
</div>
</div> 
</body>




views.py

from django.shortcuts import render
def bmi(request):
    context={}
    context['bmi']= "0"
    context['w'] = "0"
    context['h']= "0"
    if request.method == 'POST':
        print("POST method is used")
        w = request.POST.get("weight",'0')
        h= request.POST.get("height",'0')
        print('requestt=',request)
        print('Weight=',w)
        print('Height=',h)
        a=float(w)
        b=float(h)
        bmi = a/(b*b)
        context['bmi']=bmi
        context['w']=w
        context['h']=h
        print('BMI=',bmi)
    return render(request,'mathapp/math.html',context)




urls.py

from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('bodymassindex/',views.bmi,name="bodymassindex"),
    path('',views.bmi,name="bodymassindexroot")
]


```

## SERVER SIDE PROCESSING: 
![alt text](<Screenshot (46).png>)


## HOMEPAGE:
![alt text](<Screenshot (45).png>)



## RESULT:
The program for performing server side processing is completed successfully.
