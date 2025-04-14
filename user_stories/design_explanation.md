# Design

## Architectural Design 

! [UML Diagram](../Images/00_Diagrams/UML-data-diagram.png)
We decided to design the system using three main classes based on the core entities 
of the platform: User, Service Provider, and Booking. These correspond to three separate 
database tables that handle different aspects of the application logic. For the User class, 
the email field serves as the primary key, as it is unique to each user and allows easy identification 
and management. This class includes attributes such as name, isCleaner, and profileImage, allowing the 
system to distinguish between regular users and cleaners, and store relevant user data. In the ServiceProvider class, 
the name field acts as the primary key, assuming that service provider names are unique identifiers for each business.
Other fields such as location, serviceType, price, and logo support the display and filtering of services offered by 
different cleaning companies. Service providers can list services using the listServices() method. 

The Booking class represents the connection between users and service providers. A unique booking ID (implied from the diagram)
would serve as the primary key, since a single user can have multiple bookings. The foreign keys in this class are:
- The email from the User class, linking the booking back to the user who created it.
- The service provider name from the ServiceProvider class, indicating which provider is responsible for fulfilling the booking.

Each booking also stores date, status, and paymentStatus to track its progress. The confirmBooking() method allows the booking to
be updated once payment is made or a provider confirms the service. This class-based structure reflects clean separation of 
concerns while maintaining strong relationships between users, providers, and their bookings. It supports scalability, 
allowing new features like cleaner availability or customer reviews to be added in the future. 

## Database Design 
! [User Registration UI](../Images/00_Diagrams/data-flow-diagram.png)
We decided to use three databases: one for users, one for service providers, and one
for bookings. For the user database, the email will serve as the primary key as it is
unique and makes it easy to track each user. In the service provider database, the
service provider name will be the primary key as that is what differentiates each
cleaning company. In the booking database the primary key will be a unique booking ID
as one user could have multiple bookings. The user email however will be the foreign
key that connects back to the user database. 

## Interface Design 

###  Iteration 1

#### Create Bookings

##### Prototype
![Select Service Prototype](../Images/01_Prototypes/new_booking/01_select_service_prototype.png)
![select_date_time_Prototype](../Images/01_Prototypes/new_booking/02_select_date_time_prototype.png)
![enter_address Prototype](../Images/01_Prototypes/new_booking/03_enter_address_prototype.png)
![select_cleaner_Prototype](../Images/01_Prototypes/new_booking/04_select_cleaner_prototype.png)
![payment_Prototype](../Images/01_Prototypes/new_booking/05_payment_prototype.png)
![booking_summary_prototype](../Images/01_Prototypes/new_booking/06_booking_summary_prototype.png)

In our prototype, the booking process is divided across multiple pages to prevent users from feeling overwhelmed by too 
many fields at once. Each page features a clean and clear layout, making it easy to follow and fill out. A monochrome 
color scheme was used to maintain a minimal and focused design.

##### Implementation (Iteration 2)
![Browse Providers Implementation UI](../Images/02_Implemented/01_Create_Bookings/01_browse_service_providers.png)
![Select Service Implementation UI](../Images/02_Implemented/01_Create_Bookings/02_select_service_type_2.png)
![Select_cleaner Implementation UI](../Images/02_Implemented/01_Create_Bookings/03_select_cleaner.png)
![Select_date/time Implementation UI](../Images/02_Implemented/01_Create_Bookings/04_select_date_time_2.png)
![Enter_address Implementation UI](../Images/02_Implemented/01_Create_Bookings/05_enter_address.png)
![Enter_payment details Implementation UI](../Images/02_Implemented/01_Create_Bookings/06_enter_payment_details.png)
![Booking_summary Implementation UI](../Images/02_Implemented/01_Create_Bookings/07_booking_summary.png)
![Confirmation pop up  Implementation UI](../Images/02_Implemented/01_Create_Bookings/08_confirmation_popup.png)

In our current implementation for Iteration 2, color has been introduced to key buttons to make them more distinct and 
improve visibility. The overall flow of the booking pages remains consistent with our prototype, with a few minor 
adjustments to enhance user experience, such as moving the cleaner selection step earlier in the process. These changes 
were made based on feedback from team members and aim to streamline the booking journey while maintaining familiarity 
with the original design.

#### Track Schedules

##### Prototype
![Tracking Bookings Prototype](../Images/01_Prototypes/managebooking_ui.png)
The Tracking Schedules section is part of our Manage/Edit Booking page, which is discussed in more detail later. 
This screen displays bookings in a sorted list, with the closest upcoming bookings shown first. In future iterations,
we are considering introducing a calendar-based UI, depending on client feedback and user needs.

##### Implementation (Iteration 2)
![Tracking Bookings Implementation UI](../Images/02_Implemented/07_Edit_Bookings/01_manage_bookings_view.png)
Our implemented UI closely follows the layout and design of our prototype.

#### Manage Payments

##### Prototype
![Payment_Prototype](../Images/01_Prototypes/new_booking/05_payment_prototype.png)
Payment is done in our new booking process, which we go in detail later. In our prototype, the user has the option of 
selecting from a range of supported payment methods, and can enter their card in manually if they desire. 

##### Implementation (Iteration 2)
![Payment Implemented UI](../Images/02_Implemented/01_Create_Bookings/06_enter_payment_details.png)
In Iteration 2, the payment page is currently a placeholder and not functional. In future iterations, we plan to 
integrate a button that redirects users to Stripe’s secure payment page. This integration will handle the entire 
payment process, including authorization and sending receipts via email.

#### Create Profiles

##### Prototype
![User Registration UI prototype](../Images/02_Implemented/04_Create_Profiles/00_login_ui_prototype.png)
![User Registration UI prototype v2](../Images/02_Implemented/04_Create_Profiles/00_login_ui_v1.png)
The login page was designed with a blue, grey and white colour scheme, accompanied by
an image with similar colours. The input fields are in proximity with each-other to
make it very easy to sign-up or sign-in. The design follows the standards and conventions
of most sign-in/sign-up pages. The fields change depending if the user has an account or
not by clicking on the link at the bottom. Everything else on the page remains to maintain
consistency.

##### Implementation (Iteration 2)
![User Registration Implemented UI](../Images/02_Implemented/04_Create_Profiles/01_sign_up_new_user.png)
![Log in User Implemented UI](../Images/02_Implemented/04_Create_Profiles/02_log_in_user.png)
The sign-up and log-in pages follow our prototype, with slight adjustments in the color scheme, including a blue hue 
for the main sign-up and log-in buttons. In the top-right corner, a new section has been added for business admins, 
allowing them to register or log in to their admin accounts. This section is highlighted in purple, aligning with the 
color scheme used for the admin page.

#### Search 

##### Prototype
![Search provider prototype](../Images/01_Prototypes/search_ui_1.png)
The search page was designed to have very simple functionality with easy to use filters
and a clean display. The search bar is situated at the top and immediately draws the eye
so the user can very quickly find what they want. Filters help users narrow their 
search down even more easily, giving them more control and customisation. 

##### Implementation (Iteration 2)
![Search provider Implemented UI v1](../Images/01_Prototypes/search_ui_2.png)
![Search_provider Implemented UI v2](../Images/02_Implemented/05_Search/01_search_provider.png)
Our implemented UI closely follows the layout of our prototype. In Version 2, the interface was updated with rounded 
elements to enhance visual appeal and improve user-friendliness.

### Iteration 2

#### Manage Booking

##### Prototype
![Manage Booking prototype UI](../Images/01_Prototypes/managebooking_ui.png)
The Manage Booking page follows our blue, white, and grey color palette. A central tab bar at the top provides access 
to this section. Bookings are listed in ascending order by date, ensuring that the closest appointments appear first.
Each booking detail features a panel on the left displaying the date, allowing users to quickly identify their bookings,
as they typically refer to them by date rather than ID.
There are three clickable buttons within each booking, each with a distinct color:
- Edit Booking
- Cancel (highlighted in red)
- Contact, which is linked to the cleaner or provider’s information, making it clear that this button is used to reach them.

##### Implementation (Iteration 2)
![Manage Booking Implemented UI](../Images/02_Implemented/07_Edit_Bookings/01_manage_bookings_view.png)
The implemented UI for the Manage booking view closely follows our prototype.

#### Cancel Booking

##### Prototype
![Cancel Booking prototype UI](../Images/01_Prototypes/cancelbooking_ui.png)
The Cancel Booking feature is a simple pop-up interface within the Manage Booking page. It displays the booking details 
along with a prominent red warning message that includes the $40 cancellation fee, ensuring users do not overlook this 
crucial information. The Confirm button is also highlighted in red for clarity.

##### Implementation (Iteration 2)
![Cancel Booking Implemented UI](../Images/02_Implemented/07_Edit_Bookings/10_cancel_booking_message.png)
The implemented UI for the Cancel Booking pop-up closely follows our prototype.

#### Edit Booking

##### Prototype
![Edit Booking prototype UI](../Images/01_Prototypes/editbooking_ui.png)
The Edit Booking feature includes four clickable fields, allowing users to modify each aspect of their 
booking individually: Service Type, Date, Time, and Address—each clearly labeled. A Confirm Changes button in blue 
ensures users can finalize their updates. Additionally, a Return to Manage Booking button provides a quick way to 
navigate back to the previous page.

##### Implementation (Iteration 2)
![Edit Cleaner Implemented UI](../Images/02_Implemented/07_Edit_Bookings/02_edit_cleaner.png)
![Edit Date/Time Implemented UI](../Images/02_Implemented/07_Edit_Bookings/03_edit_date_time.png)
![Edit Address Implemented UI](../Images/02_Implemented/07_Edit_Bookings/04_edit_address.png)
Our implemented UI differs slightly from the prototype, as we reused assets from the Make a New Booking screens to save 
time and resources. This approach also made sense from a design perspective, as it maintains consistency and leverages 
elements users are already familiar with.

#### Messaging 

##### Prototype
![Messaging Feature prototype](../Images/01_Prototypes/chat_ui.png)
From the Manage Booking screen, users can tap Contact to message or call their assigned cleaner or provider 
for their appointment. The Chat page features a familiar UI, displaying the cleaner’s name in bold along with their 
profile picture. A call button is placed next to their name for users who prefer calling. On the right side of the chat 
box, a booking information card provides a quick overview of the appointment details. Additionally, an Edit Booking 
button is available, allowing users to make changes directly from this page without needing to navigate back.
Additionally, a return to Manage booking is also provided to navigate back to the previous page.

The Chat feature, being a lower-priority user story, was deferred to the next iteration and does not have a implemented
UI yet. 

#### Reviews

The Reviews feature did not have a prototype UI; instead, it was designed and implemented directly in the current 
iteration based on team discussions and design guidelines

##### Implementation (Iteration 2)
![Review Button Implemented UI](../Images/02_Implemented/09_Reviews/01_view_service_providers.png)
The option to review service providers is conveniently located on the screen where users select a provider. Button to 
view all existing reviews are also displayed here. Each service provider has a rating out of 5, calculated as the 
average of all their submitted reviews.

![Submit a review Implemented UI](../Images/02_Implemented/09_Reviews/02_submit_review.png)
Submitting a review is done through a pop-up that features an interactive star rating system, allowing users to click 
and select their rating. Half-star ratings are supported for greater precision. Users can also include a text comment 
to share more about their experience.

![All Reviews Implemented UI](../Images/02_Implemented/09_Reviews/03_all_reviews.png)
The All Reviews page displays only the reviews associated with a specific service provider. Each review shows the name
of the user who submitted it, along with their profile picture if available.

#### Eco-friendly

The Eco-Friendly feature did not have a prototype UI; instead, it was designed and implemented directly in the current 
iteration based on team discussions and design guidelines.

##### Implementation (Iteration 2)
![Eco-Friendly Implemented UI](../Images/02_Implemented/10_Eco_Friendly/01_eco_friendly_icon.png)
An eco-friendly icon was added to service providers as a visual indicator. The green icon is displayed above the 
provider’s name.

#### Admin Dashboard

The Admin Dashboard did not have a prototype UI; instead, it was designed and implemented directly in the current 
iteration based on team discussions and design guidelines.

##### Implementation (Iteration 2)
![Admin Sign Up Implemented UI](../Images/02_Implemented/11_Admin_Dashboard/01_sign_up_admin_account.png)
To visually distinguish the admin interface from regular user accounts, a purple and black color scheme was used. 
This choice gives the admin UI a bolder and more professional appearance.

![Register Business Implemented UI](../Images/02_Implemented/11_Admin_Dashboard/02_register_new_business.png)
As part of the onboarding process, the business admin is guided through a 5-step setup where they enter their business
details and provide the necessary information to get started. Each button in the process is large and clearly labeled. 
To ensure the correct flow and prevent steps from being skipped, only one button is active (and highlighted) at a time.

![Add Business Details Implemented UI](../Images/02_Implemented/11_Admin_Dashboard/03_add_business_details.png)
![Add Cleaner Implemented UI](../Images/02_Implemented/11_Admin_Dashboard/04_add_first_cleaner.png)
![Add Service Implemented UI](../Images/02_Implemented/11_Admin_Dashboard/05_add_first_service.png)
![Add Eco Status Implemented UI](../Images/02_Implemented/11_Admin_Dashboard/06_add_eco_status.png)
![Add Logo Implemented UI](../Images/02_Implemented/11_Admin_Dashboard/07_add_logo.png)
![Register Done Implemented UI](../Images/02_Implemented/11_Admin_Dashboard/08_register_done.png)
Each button opens a pop-up where the admin can enter all the required details for that step.

![Admin Dashboard Implemented UI](../Images/02_Implemented/11_Admin_Dashboard/09_admin_dashboard.png)
![Add new Service Implemented UI](../Images/02_Implemented/11_Admin_Dashboard/10_add_new_service.png)
This is the main dashboard for admins, featuring a visual indicator that clearly marks it as the admin view, along with 
the business name displayed at the top. The header tab provides access to all the pages available on the admin site. 
On the left, admins can view currently active services and the names of assigned cleaners, with the option to delete 
each row directly. On the right side of the page, there are buttons to add a new service or a new cleaner. In 
Iteration 2, if admins wish to make changes to an existing service or cleaner, they must delete the row and add a new 
entry. In future iterations, we plan to implement an Edit functionality for more flexibility.

