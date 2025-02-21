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
## Add favorites / Unfavorites

## Booking
## Cancel booking
## Cancel guest reservation
## Delete properties
## Filter location by condition