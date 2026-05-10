# Mermaid Diagram Pack

This directory documents the project with Mermaid diagrams derived from the implemented codebase.
Each Mermaid diagram has a PlantUML counterpart with the same basename and a `.puml` extension.

## Reading order

1. `01-system-context.mmd` - actors, major services, and integration boundaries
2. `02-deployment-runtime.mmd` - runtime/deployment topology and shared assets
3. `03-backend-api-components.mmd` - backend layering and internal components
4. `04-backend-domain-class.mmd` - persistent domain model and associations
5. `05-auth-request-flow.mmd` - login, local auth persistence, and protected navigation
6. `06-appointment-booking-sequence.mmd` - patient booking workflow and doctor-side updates
7. `07-appointment-state-flow.mmd` - appointment lifecycle states and the actors that move them
8. `08-scan-upload-inference-sequence.mmd` - end-to-end AI scan workflow
9. `09-consumer-processing-activity.mmd` - internal worker activity for inference jobs
10. `10-rabbitmq-and-async-components.mmd` - queueing, scheduler, and notification subsystems
11. `11-notification-state-flow.mmd` - notification persistence, push delivery, and read/delete lifecycle
12. `12-frontend-route-data-flow.mmd` - route/page orchestration and frontend data flow

## Source anchors

- Backend bootstrap: `../dizertatie-ie-2026-backend/index.js`
- Backend associations: `../dizertatie-ie-2026-backend/models/index.js`
- Scan lifecycle: `../dizertatie-ie-2026-backend/services/scan-service.js`
- RabbitMQ setup: `../dizertatie-ie-2026-backend/services/rabbitmq-service.js`
- Scan result handling: `../dizertatie-ie-2026-backend/services/scan-result-service.js`
- Notification pipeline: `../dizertatie-ie-2026-backend/services/notification-service.js`
- Follow-up reminders: `../dizertatie-ie-2026-backend/services/follow-up-reminder-service.js`
- Blog semantic search: `../dizertatie-ie-2026-backend/controllers/blog-controller.js`
- Consumer runtime: `../dizertatie-ie-2026-consumer/worker.py`
- Consumer routing and model loading: `../dizertatie-ie-2026-consumer/inference.py`, `../dizertatie-ie-2026-consumer/config.py`
- Frontend shell/auth: `../dizertatie-ie-2026-frontend/app/root.jsx`, `../dizertatie-ie-2026-frontend/app/utils/auth.js`
- Frontend appointments: `../dizertatie-ie-2026-frontend/app/components/appointments/create-appointment.jsx`
- Frontend scans: `../dizertatie-ie-2026-frontend/app/components/scans/create-scan.jsx`, `../dizertatie-ie-2026-frontend/app/pages/ai-scan.jsx`
- Frontend notifications: `../dizertatie-ie-2026-frontend/app/pages/notifications.jsx`

## Notes

- The scan flow diagrams reflect the current implemented contract, including scan-level `bodyPart` and `imageType` in the RabbitMQ job payload.
- The frontend scan result diagrams reflect the current multi-model result shape with `modelKey` and `routeKey`.
- If the code changes, update the relevant Mermaid file instead of expanding one diagram until it becomes unreadable.

## New PlantUML diagrams in Romanian

- `12-cazuri-de-utilizare.puml` - diagrama de cazuri de utilizare
- `13-activitate-flux-pacient.puml` - diagrama de activitate pentru fluxul pacientului
- `14-masina-de-stari-programare.puml` - diagrama de masina de stari pentru programari
- `15-interactiune-programare-follow-up.puml` - diagrama de interactiune pentru programare si follow-up
- `16-componente-arhitectura.puml` - diagrama de componente a platformei
- `17-relatii-entitati-erd.puml` - diagrama de relatii dintre entitati
