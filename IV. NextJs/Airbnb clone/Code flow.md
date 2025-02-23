## Register
#### Register by email & password
![[register-flow.png]]
## Login
#### Login by email & password
![[login-flow.png]]
- After login successful, user's informations are saved into ServerSesson of Next Auth(just email & password). If we want to show full user's infor., we need to get it by  accessing to databases by prisma (query by email).
#### Login/ Register with GG & Github
See theory and flow at: [[NextAuth.Js]]
## Add Listing
User click "Airbnb your/my home" -> show Rent modal -> fill form -> submit -> request ('/api/listings', data) -> take data from body -> create listing & save to database -> return response listings -> refesh router, reset modal, step step back to 0, close rent modal
![[add-listings-flow.png]]
## Add favorites / Unfavorites
User click on Heart Button -> invoke toggleFavorite from useFavorite -> check user login ? 'yes' : 'no' -> no, show login modal. yes, check liked or not ? 'yes': 'no'-> yes, delete from favorited list. no, add to favorited list -> handle complete -> refresh router, toast success & change color of Heart Button
![[add:delete favorite-id.png]]
## Booking
User choose start date & end date -> click Reserve ->server handle info-> direct to My trips page and show success
![[booking-flow.png]]
## Cancel booking
At trip pages, user click on 'cancel reservation'->invoke onCancel function->send request to server-> server check, delete and response -> show noti
![[cancel-booking-flow.png]]
## Cancel guest reservation
## Delete properties
## Filter location by condition