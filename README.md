# Simple.Theater.Reservation.System

This was a project I did when I started to know Java in 2022.👩‍💻 The project requirements were designed by my professor in Object-Oriented Design course.

It's just a command line interface program but I really enjoyed the process of doing it. 

## general design

<img width="300" alt="Screenshot 2024-04-03 at 8 21 33 PM" src="https://github.com/MirandaLyu/Simple.Theater.Reservation.System/assets/115821003/06d48bf3-2b2d-44ca-b33a-401305b96cee">

This is the UML diagram for the program.

It tried to apply MVC architecture concepts where Row, Seat, Theater and Person are like the Model, ReservationService and ReservationSystem are like the Controller and command line interface is like the View.

What I like most about this project is that the theater map was achieved by overriding layers of toString() functions. The below are toString() functions in Seat, Row and Theater classes. Row is composed of Seat, and Theater is composed of Row.

<img width="170" alt="Screenshot 2024-04-03 at 9 34 27 PM" src="https://github.com/MirandaLyu/Simple.Theater.Reservation.System/assets/115821003/65c77683-2e46-4e38-8ecb-53bbde18c6fc">
<img width="190" alt="Screenshot 2024-04-03 at 9 34 47 PM" src="https://github.com/MirandaLyu/Simple.Theater.Reservation.System/assets/115821003/58aadcfa-11a9-4443-af99-f3b421b7956b">
<img width="250" alt="Screenshot 2024-04-03 at 10 03 34 PM" src="https://github.com/MirandaLyu/Simple.Theater.Reservation.System/assets/115821003/6f19112b-7be6-4f89-bfb9-35e2de5db10a">

Together they provide a quick but cute way to present theater seats 🎥 :

<img width="140" alt="Screenshot 2024-04-03 at 8 06 20 PM" src="https://github.com/MirandaLyu/Simple.Theater.Reservation.System/assets/115821003/93ca593a-f3be-4023-9829-c219da56325f">

## how the system works

For example, I can reserve 2 seats under the name "Miranda", and the system will allocate 2 seats for me in the middle of the room:

<img width="200" alt="Screenshot 2024-04-03 at 8 08 53 PM" src="https://github.com/MirandaLyu/Simple.Theater.Reservation.System/assets/115821003/967734c0-80a0-4c89-9f32-07de21dca4da">

And then I reserve 7 seats under the name "Zoe". The system will give seats for me on an adjacent row:

<img width="200" alt="Screenshot 2024-04-03 at 8 09 38 PM" src="https://github.com/MirandaLyu/Simple.Theater.Reservation.System/assets/115821003/01c63222-4a9b-4453-96a8-9343214e000c">

And also I can reserve 3 seats under the name "Maggie" and choose I want wheelchair accessibility, then the system will arrange me at the wheelchair row:

<img width="200" alt="Screenshot 2024-04-03 at 8 10 15 PM" src="https://github.com/MirandaLyu/Simple.Theater.Reservation.System/assets/115821003/099a95fb-a883-4a99-8de1-557a6db08e17">

Ok, so you probably can get a sense of the seating rule here. The system implemented a rule to provide seats for users automatically. These seats are assigned beginning from the middle row and spread towards the first and last row and people are seated together. The 5th and 9th rows are wheelchair rows; if all other seats are filled up, the system will release these two rows as well.

## Thoughts

I admit that this kind of automatic rule feels very old style and a bit silly. 🐿️

But on the second thought, these rules may be more efficient than people choosing seats for themselves, right? (hope I'm not too crazy here) Do people really care that much about where to seat when watching a movie?

I think this is also something I like about designing this kind of system. Different rules really shape different systems.

## ways to improve

Undoubtedly, there are many places that can improve in this system, such as:
* when the number of reserve is over a row's capacity, how to make seats for these people
* maybe the automatic seating which begins at the center of a row more makes sense
* maybe should provide an option for users to express their preference of seating at the front or back
