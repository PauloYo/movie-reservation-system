User 1:N Reservation

Movie 1:N Showtime

TheaterRoom 1:N Seat

TheaterRoom 1:N Showtime

TheaterRoom 1:N TheaterRoomExhibitionType

ExhibitionType 1:N Showtime

ExhibitionType 1:N TheaterRoomExhibitionType

TheaterRoom N:N ExhibitionType (via TheaterRoomExhibitionType)

SeatCategory 1:N Seat

Reservation 1:N SeatReservation

Seat 1:N SeatReservation

TicketType 1:N SeatReservation

SeatReservation 1:1 Ticket

Reservation 1:N Payment
