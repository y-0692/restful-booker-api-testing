# API Analysis

## Base URL

https://restful-booker.herokuapp.com

## Available APIs

| API | Method | Purpose |
|------|---------|---------|
| /auth | POST | Generate authentication token |
| /booking | GET | Retrieve booking IDs |
| /booking | POST | Create booking |
| /booking/{id} | GET | Retrieve booking details |
| /booking/{id} | PUT | Update booking |
| /booking/{id} | PATCH | Partial update booking |
| /booking/{id} | DELETE | Delete booking |

## Authentication

Required for:
- Update Booking
- Partial Update Booking
- Delete Booking

## Booking Fields

- firstname
- lastname
- totalprice
- depositpaid
- bookingdates
  - checkin
  - checkout
- additionalneeds

## Expected Response

Create Booking:
- bookingid
- booking object
