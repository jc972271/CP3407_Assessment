# User story title: Create bookings

## Priority: 10 
Essential component of the program. User must be able to book appointments with the service provider.
This requires a database to connect to and update.

## Estimation: 5 days

1. Liam Whiting - 4 days
2. Hayden West - 4 days
3. Danny Zaw - 5 days
4. Salvin George - 5 days

## Assumptions (if any):
Assumption 1: Available slots will be updated in real time. 
Assumption 2: Canceled slots will be instantly available for others.
Assumption 3: Users can book up to 4 weeks in advance.
Assumption 4: Same day bookings will not be available. 

## Description:
Allow users to create appointments efficiently.
You need to keep all versions here so that your instructor/marker can see your changes easily. 
In a real project, your older versions could be viewed via commits.


## Tasks, see chapter 4.

1. Task 1: Create SQL database for users, Estimation 1 day/s
2. Task 2: Create SQL database for cleaners, Estimation 1 day/s
3. Task 3: Create SQL database for bookings, Estimation 1 day/s
4. Task 4: Link databases together, Estimation 1 day/s
5. Task 5: Create UI for creating the bookings, Estimation 1 day/s


# UI Design:
![Select Service](../Images/01_Prototypes/new_booking/01_select_service_prototype.png)
![Select time](../Images/01_Prototypes/new_booking/02_select_date_time_prototype.png)
![Enter address](../Images/01_Prototypes/new_booking/03_enter_address_prototype.png)
![Select cleaner](../Images/01_Prototypes/new_booking/04_select_cleaner_prototype.png)
![Payment](../Images/01_Prototypes/new_booking/05_payment_prototype.png)
![Booking summary](../Images/01_Prototypes/new_booking/06_booking_summary_prototype.png)

# Completed:
The booking page was completed and then developer testing was performed.

## Developer Testing
You can see in the image below that all the details of the testing booking has been successfully
tracked.  
![Data entry](../Images/02_Implemented/01_Create_Bookings/09_database_write.png)  
![Booking data structure](../Images/02_Implemented/01_Create_Bookings/11_booking_datatype.png)  

## User Testing  
We tested each step of the booking process, ensuring data flows correctly and all the
information is displayed on the final page correctly.
In order to test the booking system, a test user account was used to browse different
bookings that were available.  
![Browse search result bookings](../Images/02_Implemented/01_Create_Bookings/01_browse_service_providers.png)  
When the user clicks book on one of the search results, it takes them to the booking page.
The first thing they select is what type of service they want, such as standard, deep or premium.  
![Select service type](../Images/02_Implemented/01_Create_Bookings/02_select_service_type_1.png)  
![Service type selected](../Images/02_Implemented/01_Create_Bookings/02_select_service_type_2.png)  
Next the user has to select a cleaner that works for the cleaning company.  
![Select cleaner](../Images/02_Implemented/01_Create_Bookings/03_select_cleaner.png)  
The user can then choose what date and time they want the cleaning service to happen.  
![Select date](../Images/02_Implemented/01_Create_Bookings/04_select_date_time_1.png)  
![Select time](../Images/02_Implemented/01_Create_Bookings/04_select_date_time_2.png)  
The user can then provide their personal details. This includes their location, the room type
and also a special notes text area that they can provide any additional information that
may help the cleaners.  
![Provide personal details](../Images/02_Implemented/01_Create_Bookings/05_enter_address.png)  
Payment details are then required to be filled out, in which the user can choose between
filling out the inputs or using stripe to complete the payment.   
![Enter payment details](../Images/02_Implemented/01_Create_Bookings/06_enter_payment_details.png)  
A summary of the booking is then displayed so that the user can check to make sure
all the details are correct.  
![Booking summary](../Images/02_Implemented/01_Create_Bookings/07_booking_summary.png)  
After making the booking, a confirmation pop-up is displayed so that the user knows that
the booking has been made successfully.  
![Confirmation](../Images/02_Implemented/01_Create_Bookings/08_confirmation_popup.png)  
The booking is then added to the bookings database so that the user can later track and edit their bookings.
