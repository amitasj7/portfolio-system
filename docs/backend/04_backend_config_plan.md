🗂️ Planned config structure (COMMENT-LEVEL DESIGN)

backend/src/config/
├── env.ts        // loads + validates environment variables
├── db.ts         // creates MongoDB connection using env config
├── session.ts    // session & cookie configuration
├── mail.ts       // email (SMTP) configuration
├── whatsapp.ts   // WhatsApp / messaging configuration



🧾 What EACH config file is responsible for (planning)

env.ts (central gatekeeper) -
// Purpose:
// - Load environment variables
// - Validate required variables
// - Convert types (string → number, boolean)
// - Export a SAFE config object

// Rules:
// - process.env used ONLY here
// - Throws error if required variable missing
// - No business logic


db.ts -
// Purpose:
// - Create MongoDB connection
// - Use env.mongoUri
// - Handle connection errors centrally

// Rules:
// - No hardcoded credentials
// - No direct process.env access


session.ts
// Purpose:
// - Configure session/cookie behavior
// - Use env.sessionSecret
// - Control cookie security flags

// Rules:
// - Centralized session settings
// - Environment-aware (dev vs prod)


mail.ts
// Purpose:
// - Configure email provider (SMTP)
// - Used by notification services

// Rules:
// - No sending logic here
// - Only transport/config setup


whatsapp.ts
// Purpose:
// - Configure WhatsApp API / webhook client
// - Store credentials and endpoints

// Rules:
// - Only configuration
// - No message logic



## Express App Bootstrap (app.ts)

🎯 Purpose of app.ts

app.ts answers one question only:
“How is the Express application configured?”

It does NOT:
Start the server
Connect to DB
Contain business logic


🧠 Responsibilities (SHORT)
app.ts responsibilities:
- Create Express app instance
- Register global middlewares
- Register base routes
- Handle unknown routes
- Export app (do NOT listen here)


🔌 Middlewares to plan (only list)
Planned middlewares:
- express.json()        // parse JSON
- express.urlencoded() // parse form data
- cors()                // allow frontend access
- morgan()              // request logging (dev only)


🛣️ Routes (planning only)
Routes registered in app.ts:
- /health        → health check
- /api           → main API router (future)


🚫 Rules (important)
Rules:
- app.ts must NOT call app.listen()
- app.ts must NOT connect to database
- app.ts must stay framework-only


Export:
- export default app


