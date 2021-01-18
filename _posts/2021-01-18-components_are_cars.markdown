---
layout: post
title:      "Components Are Cars"
date:       2021-01-18 15:35:42 +0000
permalink:  components_are_cars
---


I've spent the last 5 months learning to program. Our last section was React and in it, we delved into the world of components. I'm a connector, meaning I naturally find connections between what is happening in different spheres of life. I've got quite a few hobbies and one of them is wrenching on pretty much anything with an engine. I've built a scooter from the ground up and installed engines in cars. I understand (to a reasonable degree) how they function.

While learning React I've noticed how components function in much the same way that cars do. While each piece of an engine has it's own properties, they do not simply serve an isolate purpose. Much in the same way, components have their own props (properties) but they do not serve a purpose on their own.  Getting even more specific, if we look at an engine "component" like a piston, we can see that it has properties such as it's bore size, and whether it's been cast or forged and the skirt. Because a piston needs to work in conjunction with the rest of the engine, these properties are not arbitraty but handed down from other parent parts of the engine, like the cylinder and block.

React components are handed props from parent components to use to ultimately acomplish the goal of creating a satisfactory user experience. When you drive a car, like most of us do, you don't really need to know what is happening under the hood to be happy with your brand new Honda CRV. You just put your foot on the gas and go! The engineers who built the car have abstracted all of the complexity away using different components of the car. Most of the time, cars even share a lot of the same components and only the ones that need to be changed are swaped out to build diferent cars! Similarly, React takes the complexity of as fully functioning application and abstracts it away using components. These components are reused where they can be and it eliminates unecessary typing for the programmer and a uniform satisfactory experience for the user.
