# Airbnb Clone - Features and Functionalities

This document outlines the core features required for the Airbnb Clone backend system. The system is designed to connect hosts who have accommodations to rent with guests seeking places to stay.

## 1. User Management (Authentication & Authorization)
* **User Registration:** Users can sign up as a Guest or a Host using email/password.
* **User Login:** Secure authentication using JWT (JSON Web Tokens).
* **Profile Management:** Users can update personal information, bio, and profile pictures.
* **Role Management:** Distinction between Guests, Hosts, and Admins.

## 2. Property Management (Places)
* **Create Listing:** Hosts can add new properties with details (title, description, price, location, amenities).
* **Update/Delete Listing:** Hosts can modify or remove their property listings.
* **Search & Filter:** Guests can search for properties based on location, price range, and available dates.
* **Image Upload:** Integration for uploading and storing property images.

## 3. Booking System
* **Check Availability:** System checks if a property is free for specific dates.
* **Create Booking:** Guests can reserve a property for a specific duration.
* **Manage Bookings:** Hosts can approve or reject booking requests; Guests can cancel bookings.
* **Booking History:** View past and upcoming trips.

## 4. Reviews and Ratings
* **Add Review:** Guests can leave text reviews and star ratings for properties they have visited.
* **View Reviews:** Public visibility of reviews on property pages to build trust.

## 5. Payment System (Mock/Integration)
* **Process Payment:** Secure handling of payments during the booking process.
* **Transaction History:** Records of payments made by guests and earnings for hosts.
