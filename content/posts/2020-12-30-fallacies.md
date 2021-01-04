---
title: "8 Deadly Sins of Distributed Systems"
date: 2020-12-30T20:07:19+01:00
draft: false
categories: Architecture
---

There are 8 deadly sins being ignored when designing and implementing distributed applications today.

- The network is reliable;
- Latency is zero;
- Bandwidth is infinite;
- The network is secure;
- Topology doesn't change;
- There is one administrator;
- Transport cost is zero;
- The network is homogeneous.

![Distribution](../../static/fallacies.jpg)

## 1. Network is reliable

Lets be honest, network is never reliable. And in most of the cases is the "scapegoat". In your standup meetings or in calls with production teams, its always network. 

#### What helps 
- Technical success message recieved (of course should be protocal agnostic if possible)
- Depending on the reqirement and throughput size, a reliable messaging medium can be used (RabbitMQ, Kafka etc.)
- Depending on the messaging medium, retry / de-duplicaion, ordering, sorting needs to be taken cared of
- And messages needs to be verified 

## 2. Latency is Zero

Latency is the inherent delay present in any communication, regardless of the size of the transmission. The total time for a communication will be

> **TotalTime = Latency + (Size / Bandwidth)**

In other words; time to cross the network in one direction. 

#### What helps 
- Optimise geography 
    - Reduce number of remote calls as much as possible
- No remote object calls (DTO's are ok)

> First Law of Distributed Object Design: "don't distribute your objects". / Martin Fowler


## 3. Bandwidth is infinite

Bandwith is the amount of data can be transfered at a certain amount of time and is limited but getting better since the beginning of the internet. 

#### What helps 
- Seperation of networks (logical) and prioritisation of bandwitdh according to the prioritisation (eg. payment service > reporting).
- When designing architecture, seperating components considering bandiwth requirements (ex. DDD Bounded Context and Aggregate patters or CQRS)

## 4. Network is secure

Security experts say if a machine is not turned off (and burried), it is not secure and penetrable. Attack vectors can vary from email attachments to unencrypted network traffic.


#### What helps 
- Continous threat model analysis and identify solutions / mitigations
- Using security principles / practises when desiging and implementing systems considering cost & benefits
- Transparcy to business, Law and HR. 


## 5. Topology doesn't change

In today's world topology is continiously changing. New security, application layers added, removed or modified. If you are working in an enterprise probably all the teams around you changing the topology this way or another. 

#### What helps 
- No hard coded adresses/names. Use DNS, Active Directory or LDAP whenever possible with cautious. 
- Using Multicast protocols if possible.
- Using ESB (also modern API Gateway's) enhances location transparency
- Test topology change tests whenever possible (Some reccomends Chaos Monkey but you need to convince your management line to install this :))


## 6. There is one administrator

Unless we are working in a very small company with one application, it is less likely to have one administrator. In todays companies there are more moving parts, complex systems, mutliple teams even companies changing giant systems. 


#### What helps 
- As there are more and more admins, posibility of frequent changes is very high. Every possible component in a distributed system must be as configurable as possible. 
- Sufficient enough logs to pinpoint production issues 
- Admins will change -> As backward compatibility is hard, running mutliple versions to be considered.
-  CI/CD helps -> Sasy to sell, difficult to build and maintain!! 

## 7. Transport cost is zero

In distributed environments, before the transport, data needs to be serialised and on the reciving system deserialised (aka. Marshaling). This bothe uses the resources of the system and adds latency to the operation. If you are in cloud, the cost will be more obvious. 

The other aspect is network transport cost. Security, lease cost and of course operation cost will come on top. 

## 8. The network is homogeneous

Networks are extremely heteregenous. Different operating systems, databases, file servers, event different cloud providers running together with on-premise systems.  

Very humbly I believe, this fallacy is obselete today (unless for a particular reason you need to implement your own protocol). Because most of the architects and developers embraces this. 

#### What helps 

- Using standard standards/protocols like REST, SOAP etc. as much as possible.
- Using  and implementing solutions that supports interoprability and standard protocols and standards.

