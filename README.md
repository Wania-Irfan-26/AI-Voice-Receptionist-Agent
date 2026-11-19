# AI Voice Receptionist
### AI-Powered Call Handling and Automated Appointment Booking

An AI-powered voice receptionist that handles incoming business calls, answers customer questions and books appointments automatically.

Built using **Vapi, Make.com and Google Calendar**, this project demonstrates how voice AI and workflow automation can work together to reduce manual front-desk tasks and simplify appointment management.

---

## 1. Project Overview

Businesses often miss potential opportunities when staff are busy attending to customers, handling daily operations or unavailable to answer incoming calls.

The AI Voice Receptionist provides an automated solution by handling incoming calls through natural voice conversations.

It can collect customer details, respond to configured business-related questions, check appointment availability and create bookings directly in Google Calendar.

The system is designed to be configurable for different appointment-based businesses.

## 2. Key Features

- **AI-Powered Call Handling:** Handles incoming calls through natural voice conversations.
- **Customer Query Handling:** Answers questions using configured business information.
- **Appointment Booking:** Collects the information required to schedule an appointment.
- **Real-Time Availability Checks:** Checks Google Calendar availability before booking.
- **Double-Booking Prevention:** Rejects occupied time slots instead of creating conflicting appointments.
- **Alternative Time Handling:** Allows callers to suggest another appointment time when their requested slot is unavailable.
- **Automated Calendar Updates:** Creates confirmed appointments directly in Google Calendar.

## 3. How It Works

The system connects voice AI with an automated backend workflow.

1. A customer calls the AI receptionist.
2. The assistant understands the customer's request and collects the required details.
3. The assistant confirms the appointment information with the caller.
4. Vapi sends the booking details to a Make.com webhook.
5. Make.com checks the requested time against Google Calendar availability.
6. If the slot is available, the workflow creates the appointment.
7. If the slot is occupied, the workflow returns an unavailable response.
8. The assistant communicates the result to the caller.

## 4. System Architecture

**Technology flow:**

Customer Call → Vapi Voice Assistant → Make.com Webhook → Google Calendar Availability Check → Booking Decision → Calendar Event / Unavailable Response

### Main Components

| Technology | Purpose |
|---|---|
| Vapi | Voice assistant, call handling and conversation management |
| Make.com | Backend workflow automation and booking logic |
| Google Calendar | Appointment availability and event management |

## 5. Appointment Booking Workflow

The Make.com scenario handles the appointment booking process.

**Workflow modules:**

- Custom Webhook: Receives appointment information from Vapi.
- Set Variable: Prepares the appointment data for the workflow.
- Google Calendar Free/Busy: Checks whether the requested time is occupied.
- Router: Directs the workflow based on availability.
- Search Events: Checks existing calendar events.
- Create Event: Creates the appointment when the slot is available.
- Webhook Response: Returns the booking outcome to Vapi.

### Booking Information

The assistant collects five main fields:

| Field | Description |
|---|---|
| caller_name | Customer's name |
| caller_phone | Customer's phone number |
| service_type | Requested service |
| appointment_date | Appointment date (YYYY-MM-DD) |
| appointment_time | Appointment time (HH:MM) |

## 6. Testing and Validation

The system was tested against different booking scenarios to validate its workflow.

| Test Scenario | Expected Behaviour |
|---|---|
| Available time slot | Appointment is created |
| Occupied time slot | Booking is rejected |
| Alternative time requested | New time can be checked |
| Duplicate booking attempt | Existing booking is not duplicated |
| Successful booking | Calendar event is automatically created |

These tests demonstrate the core booking and availability logic of the prototype.

## 7. Business Applications

The system can be configured for appointment-based businesses, including:

- Dental and medical clinics
- Salons and beauty businesses
- Consulting services
- Professional service providers
- Other businesses that manage customer appointments

Business-specific information, operating hours, services and appointment rules can be configured according to requirements.

## 8. Potential Business Benefits

- Reduce missed call opportunities.
- Reduce repetitive front-desk tasks.
- Make appointment scheduling more efficient.
- Help prevent scheduling conflicts.
- Provide customers with an automated calling experience.

These are intended benefits. Actual business outcomes depend on deployment, configuration and usage.

## 9. Future Improvements

Potential extensions include:

- SMS appointment confirmations.
- Automated appointment reminders.
- Staff notifications for new bookings.
- CRM integration.
- Call history and analytics dashboard.
- Multi-business configuration and management.

## 10. Project Status

**Working Prototype**

The core voice interaction, calendar availability checking and automated appointment booking workflow have been implemented and tested.

The system can be adapted and configured for individual businesses before production deployment.

---

### Built With

Vapi • Make.com • Google Calendar

**Developed by Wania Irfan**

AI Automation | Voice AI | Workflow Automation
