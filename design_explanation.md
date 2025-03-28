# Design

## Architectural Design 


## Database Design 
! [User Registration UI](Images/data-flow-diagram.png)
We decided to use three databases: one for users, one for service providers, and one
for bookings. For the user database, the email will serve as the primary key as it is
unique and makes it easy to track each user. In the service provider database, the
service provider name will be the primary key as that is what differentiates each
cleaning company. In the booking database the primary key will be a unique booking ID
as one user could have multiple bookings. The user email however will be the foreign
key that connects back to the user database.

## Interface Design 
! [User Registration UI prototype](../Images/login_ui_1.png)
The login page was designed with a blue, grey and white colour scheme, accompanied by
an image with similar colours. The input fields are in proximity with each-other to
make it very easy to sign-up or sign-in. The design follows the standards and conventions
of most sign-in/sign-up pages. The fields change depending if the user has an account or
not by clicking on the link at the bottom. Everything else on the page remains to maintain
consistency.

! [Search page prototype](../Images/search_ui_1.png)
The search page was designed to have very simple functionality with easy to use filters
and a clean display. The search bar is situated at the top and immediately draws the eye
so the user can very quickly find what they want. Filters help users narrow their 
search down even more easily, giving them more control and customisation. 