# EntityUser

## Attributes
- `id` (`INTEGER`): Unique identifier for the user
- `username` (`VARCHAR(50)`): The user's username
- `email` (`VARCHAR(255)`): The user's email address
- `password` (`VARCHAR(255)`): The user's password (hashed)
- `role` (`VARCHAR(20)`): The user's role (admin/user)

# EntityMovie

## Attributes
- `id` (`INTEGER`): Unique identifier for the movie
- `title` (`VARCHAR(255)`): The title of the movie
- `description` (`TEXT`): A brief description of the movie
- `duration` (`INTEGER`): The duration of the movie in minutes
- `genre` (`VARCHAR(100)`): The genre of the movie
- `poster_url` (`VARCHAR(500)`): URL to the movie's poster image

# EntityTheaterRoom

## Attributes
- `id` (`INTEGER`): Unique identifier for the theater room
- `name` (`VARCHAR(100)`): The name of the theater room
- `capacity` (`INTEGER`): The seating capacity of the theater room

# EntityExhibitionType

## Attributes
- `id` (`INTEGER`): Unique identifier for the exhibition type
- `name` (`VARCHAR(50)`): The name of the exhibition type (e.g., 2D, 3D, IMAX)

# EntityTheaterRoomExhibitionType

## Attributes
- `theater_room_id` (`INTEGER`): The ID of the theater room
- `exhibition_type_id` (`INTEGER`): The ID of the exhibition type

# EntitySeat

## Attributes
- `id` (`INTEGER`): Unique identifier for the seat
- `theater_room_id` (`INTEGER`): The ID of the theater room to which the seat belongs
- `seat_row` (`VARCHAR(5)`): The row of the seat within the theater room (A, B, C, etc.)
- `seat_column` (`INTEGER`): The column of the seat within the theater room (1, 2, 3, etc.)
- `seat_category_id` (`INTEGER`): The ID of the category to which the seat belongs

# EntitySeatCategory

## Attributes
- `id` (`INTEGER`): Unique identifier for the seat category
- `name` (`VARCHAR(50)`): The name of the seat category (e.g., Regular, VIP)

# EntitySeatReservation

## Attributes
- `id` (`INTEGER`): Unique identifier for the seat reservation
- `reservation_id` (`INTEGER`): The ID of the reservation associated with the seat reservation
- `seat_id` (`INTEGER`): The ID of the seat being reserved
- `ticket_type_id` (`INTEGER`): The ID of the ticket type for the seat reservation
- `base_price` (`DECIMAL(10,2)`): The base price for the seat reservation
- `discount_amount` (`DECIMAL(10,2)`): The discount applied to the seat reservation (if any)
- `final_price` (`DECIMAL(10,2)`): The final price for the seat reservation after applying any discounts
- `status` (`VARCHAR(20)`): The status of the seat reservation (e.g., reserved, canceled)

# EntityShowtime

## Attributes
- `id` (`INTEGER`): Unique identifier for the showtime
- `movie_id` (`INTEGER`): The ID of the movie being shown
- `theater_room_id` (`INTEGER`): The ID of the theater room where the showtime is taking place
- `exhibition_type_id` (`INTEGER`): The ID of the exhibition type for the showtime
- `starts_at` (`DATETIME`): The date and time of the showtime
- `ends_at` (`DATETIME`): The date and time when the showtime ends
- `status` (`VARCHAR(20)`): The status of the showtime (e.g., scheduled, canceled)

# EntityReservation

## Attributes
- `id` (`INTEGER`): Unique identifier for the reservation
- `user_id` (`INTEGER`): The ID of the user who made the reservation
- `showtime_id` (`INTEGER`): The ID of the showtime for which the reservation is made
- `total_price` (`DECIMAL(10,2)`): The total price for the reservation
- `status` (`VARCHAR(20)`): The status of the reservation (e.g., pending, confirmed, canceled)
- `created_at` (`DATETIME`): The date and time when the reservation was created
- `expires_at` (`DATETIME`): The date and time when the reservation expires if not confirmed

# EntityTicket

## Attributes
- `id` (`INTEGER`): Unique identifier for the ticket
- `seat_reservation_id` (`INTEGER`): The ID of the seat reservation associated with the ticket
- `code` (`VARCHAR(100)`): A unique code for the ticket
- `issued_at` (`DATETIME`): The date and time when the ticket was issued
- `status` (`VARCHAR(20)`): The status of the ticket (e.g., valid, used, canceled)

# EntityTicketType

## Attributes
- `id` (`INTEGER`): Unique identifier for the ticket type
- `name` (`VARCHAR(50)`): The name of the ticket type (e.g., Adult, Child, Senior)
- `price_multiplier` (`DECIMAL(4,2)`): The price multiplier for the ticket type (e.g., 1.0 for Adult, 0.5 for Child)

# EntityPayment

## Attributes
- `id` (`INTEGER`): Unique identifier for the payment
- `reservation_id` (`INTEGER`): The ID of the reservation associated with the payment
- `amount` (`DECIMAL(10,2)`): The amount paid
- `payment_method` (`VARCHAR(50)`): The method of payment (e.g., credit card, PayPal)
- `payment_status` (`VARCHAR(20)`): The status of the payment (e.g., pending, completed, failed)
- `paid_at` (`DATETIME`): The date and time when the payment was made
