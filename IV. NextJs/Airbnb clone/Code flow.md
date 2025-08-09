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
At page My reservations, click on 'Cancel guest reservation' -> invoke action onCancel -> get id & setDeleting ID -> send request to server with method DELETE-> server check user ID, take id from params, check it -> delete in database-> return response
![[cancel-guest reser-flow.png]]
## Delete properties
![[delete-properties-flow.png]]
## Filter location by condition
Click on search bar in header menu -> show search modal -> fill full infor -> click on submit-> init current query at the moment -> update currentQuery with these value: location, guestCount, roomCount, bathroomCount, dateRange(after parse to ISO)-> direct to url by route.push. At home page show filter info by getListings(searchParams)
![[filter-flow.png]]

## Upload Img
Use cloudinary cloud
