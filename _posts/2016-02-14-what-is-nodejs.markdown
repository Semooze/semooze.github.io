---
layout: post
title:  "Hello Node.js !"
date:   2016-02-14 12:35:00 +0700
categories: programming
tags: node.js
img: "../images/nodejs.png"
excerpt_separator: <!--more-->
guid: "ccbb0c56-da58-4238-a20b-23524fe01c21"
---
Node.js คือ ?
============

[Node.js][node.js] ไม่ใช่ภาษาโปรแกรมใหม่แต่อย่างใด แต่เป็น platform ที่ทำให้สามารถ รัน Java script บนฝั่งเซิร์ฟเวอร์ได้ โดยเพิ่มเติมไลบรารี่ที่เกี่ยวข้องกับการจัดการไฟล์ การรับส่งข้อมูล และอื่นๆ

Node.js เกิดขึ้นได้อย่างไร ?
========================

Ryan Dahl เขียน Node.js ขึ้นในปี ค.ศ. 2009 โดย Node ทำงานอยู่บน  V8 JavaScript engine

V8 JavaScript engine คืออะไร ?
=============================

เป็น Javascript engine ที่เขียนขึ้นด้วยภาษา C++ นำมาใช้ใน Google [chrome browser][chrome-browser]

ระบบของ Node.js
================

**Single thread**

การทำงานจะใช้เพียง Thread เดียว  
*หากไม่ได้ใช้ module [cluster][cluster] หรือ [webworker-threads][webworker-threads]

**Event-driven**

การทำงานจะเป็นแบบ [Event-based][event-based] คือ จะทำงานตามที่ได้รับมอบหมายเพียงอย่างเดียว ไม่มีการรอผลลัพธ์จากการทำงานที่ไม่เกี่ยวข้อง ตัวอย่างเช่น พยาบาลคนหนึ่งมีหน้าที่แจกแบบฟอร์มตรวจสุขภาพ และบันทึกข้อมูลลงคอมพิวเตอร์ เมื่อมีผู้ป่วยมาเข้าคิวเพื่อรับแบบฟอร์ม พยาบาลจะแจกแบบฟอร์มให้ หลังจากได้รับแบบฟอร์มแล้วเขาต้องไปตรวจสุขภาพตามห้องตรวจต่างๆด้วยตัวเอง ระหว่างนี้พยาบาลจะไม่รอแต่จะแจกแบบฟอร์มให้คนถัดไปทันที เมื่อชายคนนั้นตรวจสุขภาพครบทุกอย่างแล้วจึงจะมาเข้าคิวอีกครั้งเพื่อให้พยาบาลบันทึกลงคอมพิวเตอร์

**Non-blocking I/O**

คำสั่งที่เกี่ยวข้องกับ I/O เช่น คิวรี่ฐานข้อมูล เรียกดูข้อมูลจากเว็บไซต์เขียนหรืออ่านไฟล์ จะมีการทำงานแบบ asynchronous คือไม่มีการหยุดการทำงาน(block) เพื่อรอผลลัพธ์จากคำสั่งเหล่านี้

จุดเด่นของ Node.jsคืออะไร
=======================

การทำงานแบบ Event-driven และ non-blocking I/O ทำให้ไม่มีการรอผลลัพธ์ที่ที่เกิดจาก I/O request เช่น เมื่อส่งคิวรี่ไปยังฐานข้อมูล DBMS จะต้องใช้เวลาสักพักในการค้นหาข้อมูลที่เราต้องการและส่งกลับมา แต่ Node.js จะไม่รอและทำงานในคำสั่งถัดไปทันที เมื่อข้อมูลที่ต้องการถูกส่งกลับมาแล้วจึงจะนำข้อมูลนั้นไปทำงานต่อ ช่วยลดเวลาที่เสียไปจากการรอผลลัพธ์

การทำงานเพียง Thread เดียวทำให้ไม่มีการ context switch ระหว่าง thread ช่วยลดเวลาที่เสียไปจาก context switch

ทั้งสามเหตุผลทำให้ Node.js ทำงานได้รวดเร็ว โดยเฉพาะเมื่อแอพพลิเคชั่นที่ต้องการสร้าง มีการเรียกใช้งาน I/O เยอะ

Node.js ใช้ ภาษา Java script ซึ่งเป็นภาษาที่นิยมใช้ในงานด้าน Frontend ช่วยลดเวลาในการศึกษาเรียนรู้ในการศึกษาภาษาใหม่

มี Libraries เสริมจำนวนมากทำให้เราไม่ต้องเสียเวลามาเขียนเอง

การติดตั้ง
==========

[LTS Version (4.3.0)][lts-version]<br>
[Stable latest version (5.6.0)][latest-version]<br>
[ลงผ่าน package manager][package-manager]<br>

ข้อมูลเพิ่มเติม
===========

[Original Node.js presentation](https://www.youtube.com/watch?v=ztspvPYybIY&noredirect=1)

[node.js]: https://nodejs.org/en/
[chrome-browser]: https://developers.google.com/v8/
[event-based]: http://code.danyork.com/2011/01/25/node-js-doctors-offices-and-fast-food-restaurants-understanding-event-driven-programming/
[lts-version]: https://nodejs.org/en/download/
[latest-version]: https://nodejs.org/en/download/stable/
[package-manager]: https://nodejs.org/en/download/package-manager/
[cluster]: https://nodejs.org/api/cluster.html
[webworker-threads]: https://www.npmjs.com/package/webworker-threads
