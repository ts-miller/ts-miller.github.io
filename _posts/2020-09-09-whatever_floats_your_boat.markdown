---
layout: post
title:      "Whatever floats your boat"
date:       2020-09-09 14:40:28 -0400
permalink:  whatever_floats_your_boat
---


This last week was a period of training wheels coming off. Gone were the helps of the preloaded rspec file and present was the wildwest of a blank VScode folder. One of the troubles I faced was getting numbers to multiply and divide as they should with appropriate decimal places. The issue was that I was attempting to return decimal values using integers. This takes me back to gradeschool math where I learned what integers were and needless to say, I had forgotten.

In code, integers can only consist of whole numbers (ex. 1, 56, 23, -234). This is a problem when you are trying to get fractional values. I had assumed that in Ruby, the name 'integer' simply was codespeak for number. If we want to be specific, a string can contain a number, an integer can contain a number and -- here we go -- a FLOAT can contain numbers. They simply are different classes that treat the numbers within them differently.

A float is a numerical class with a decimal point. To allow my equation to output decimals correctly, I first needed to convert it to a float using the 'to_f' function. This is a great way to convert integer variables to floats for equations but if I wanted a float from the beginning there is a better way to do it.

Rather than:

    number = 9
    number.to_f

I can simply add a decimal to the end:

    number = 9.0

Ruby will now recognize 'number'  as a float class.

It was a quick and minor problem that was sorted quickly but I thought it was fascinating and I think deserves reflection!
