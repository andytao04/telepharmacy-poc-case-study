# Design Decisions & Lessons

## 1. Use Flutter for cross-platform delivery

One objective was to support both Android and iOS without maintaining separate native applications.

Flutter allowed the prototype to use a shared codebase across both platforms, reducing duplicated development effort.

## 2. Design around the patient's own device

A key difference from the existing branch-dependent telepharmacy setup was the ability for users to access the workflow directly from their own mobile device.

This shaped the product flow around:

- registration;
- preliminary assessment;
- pharmacist consultation;
- verification;
- collection-location support.

## 3. Keep selected patient data on-device

The prototype used local device storage for selected patient-side information.

This reduced the amount of patient information sent to the backend while still allowing the server to manage account and workflow records needed for the PoC.

## 4. Separate client and server responsibilities

The Flutter app focused on:

- user interaction;
- device capabilities;
- chatbot;
- video;
- geolocation;
- QR-code presentation.

The Flask backend focused on:

- authentication;
- pharmacist verification;
- account lifecycle;
- order-related data access.

This separation made the prototype easier to reason about and evolve.

## 5. Use existing platforms for specialized capabilities

Rather than building every capability from scratch, the PoC integrated established services/libraries for functions such as chatbot interaction, video conferencing, notifications, location, and QR generation.

For a proof-of-concept, this allowed effort to stay focused on the end-to-end telepharmacy workflow.

## 6. Treat the prototype as a validation vehicle

The goal was not to produce a production healthcare platform.

The PoC was used to validate that the proposed workflow could be implemented as a working mobile experience and demonstrated in a relevant industry context.

## Lessons learned

The project reinforced several solution-design principles:

- begin from the operational/user problem rather than the technology;
- use cross-platform frameworks selectively when speed of validation matters;
- separate user experience from backend workflow logic;
- integrate existing services where they accelerate validation;
- distinguish clearly between PoC architecture and production architecture;
- design technical demonstrations so industry stakeholders can understand the user and operational value, not only the implementation.