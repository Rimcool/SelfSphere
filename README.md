



    



Vision
“Every game you play reveals a piece of you. Every choice you make shapes your digital twin.”
SelfSphere is a personality-discovery mobile game that helps users understand themselves through immersive scenarios, quizzes, and interactive storytelling. As you play, an AI Twin evolves alongside you — learning your communication style, values, and personality — so it can eventually speak and act on your behalf.

Dark Mode — Void Runner	Feminine Mode — Velvet Dream
Cyberpunk · Neon-Noir · Immersive	Dreamy · Editorial · Ethereal
Cyan glows · Glassmorphism · 3D depth	Blush tones · Soft bokeh · Watercolor



Core Features
Personality Discovery Engine
•13-Dimensional Persona Mapping — Core Values, Traits, Emotional Triggers, Passions, Perspectives, Beliefs, Success Definition, Coping Mechanisms, Natural Strengths, Cognitive Drains, Personal Boundaries, Aesthetic Identity
•Scenario-Based Games — Branching narratives that reveal who you truly are
•Visual Persona Radar — Interactive chart showing your unique personality fingerprint
AI Twin
•Evolving Digital Replica — Learns from every game session and user correction
•Smart Auto-Reply — Handles messages when you’re busy, in your authentic voice
•Persona-Driven Responses — Communicates based on your actual personality data
•Privacy-First — On-device processing, encrypted cloud sync
Dual-Theme Cinematic UI
•Dark Mode — Neon accents, glassmorphism, particle effects, grid-floor perspective
•Feminine Mode — Soft gradients, bokeh orbs, watercolor washes, editorial typography
•Cinematic Animations — Slow, film-like transitions (600ms–1200ms)



Architecture
SelfSphere/
│
├──  client/                    # React Native + Expo App
│   ├── app/                     # Expo Router file-based routing
│   │   ├── auth/               # Login, Register, Onboarding
│   │   ├── (tabs)/             # Main app screens
│   │   │   ├── index.tsx       # Home Dashboard
│   │   │   ├── games.tsx       # Game Hub
│   │   │   ├── twin.tsx        # AI Twin Chat
│   │   │   ├── profile.tsx     # User Profile
│   │   │   └── settings.tsx    # App Settings
│   │   └── _layout.tsx         # Root layout with theme provider
│   │
│   ├── components/
│   │   ├── ui/                 # Reusable UI primitives
│   │   │   ├── Input.tsx       # Glassmorphic input field
│   │   │   ├── Button.tsx      # Gradient CTA button
│   │   │   ├── Card.tsx        # Glass card with blur
│   │   │   └── Avatar.tsx      # Glowing avatar component
│   │   ├── game/               # Game-specific components
│   │   ├── twin/               # AI Twin chat components
│   │   └── theme/              # Theme toggle, mode provider
│   │
│   ├── hooks/
│   │   ├── usePersona.ts       # Persona data & updates
│   │   ├── useTwin.ts          # Twin interaction logic
│   │   └── useTheme.ts         # Dark / Feminine mode
│   │
│   ├── constants/
│   │   ├── colors.ts           # Theme color tokens
│   │   ├── typography.ts       # Font scale & styles
│   │   └── animations.ts       # Shared animation configs
│   │
│   └── assets/
│       ├── fonts/              # Space Grotesk, Inter
│       ├── images/             # Backgrounds, illustrations
│       └── animations/         # Lottie files
│
├──  server/                     # Node.js + Express Backend
│   ├── config/
│   │   ├── database.js         # MongoDB connection
│   │   └── passport.js         # Google OAuth strategy
│   │
│   ├── models/
│   │   ├── User.js             # Auth, profile, settings
│   │   ├── Persona.js          # 13-dimension personality vector
│   │   ├── Scenario.js         # Game scenarios & branching logic
│   │   ├── GameSession.js      # Session tracking & scoring
│   │   └── TwinProfile.js      # AI Twin training data
│   │
│   ├── routes/
│   │   ├── auth.js              # Register, Login, Google OAuth
│   │   ├── persona.js           # CRUD personality data
│   │   ├── game.js              # Scenario fetch, answer submit
│   │   ├── twin.js              # Twin message generation
│   │   └── user.js              # Profile, settings update
│   │
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── personaController.js
│   │   ├── gameController.js
│   │   ├── twinController.js
│   │   └── userController.js
│   │
│   ├── middleware/
│   │   ├── auth.js              # JWT verification
│   │   └── errorHandler.js
│   │
│   ├── services/
│   │   ├── twinEngine.js        # AI Twin response generation
│   │   ├── personaScorer.js     # Game answer → persona vector
│   │   └── openaiService.js     # OpenAI API integration
│   │
│   ├── utils/
│   │   └── personaDimensions.js # 13-dimension definitions
│   │
│   └── index.js                 # Server entry point
│
└──  README.md



Tech Stack
Layer	Technology	Purpose
Frontend	React Native + Expo	Cross-platform mobile app
Routing	Expo Router	File-based navigation
Styling	NativeWind / StyleSheet	Tailwind-like utility classes
State	Zustand	Lightweight global state
Animations	React Native Reanimated	60fps cinematic transitions
Backend	Node.js + Express	REST API server
Database	MongoDB + Mongoose	Document store for personas
Auth	JWT + Passport.js + Google OAuth	Secure authentication
AI	OpenAI GPT-4 API	Twin personality modeling
Storage	Cloudinary / AWS S3	User avatars, game assets



Persona Dimensions
The SelfSphere engine maps users across 13 dimensions, each scored 0–100:
#	Dimension	Discovered Via
1	Core Values	Moral dilemma scenarios
2	Personality Traits	Psychometric mini-games
3	Emotional Triggers	Reaction-time stress tests
4	Passions	Interest-sorting puzzles
5	Perspective	Philosophy branching stories
6	Values & Beliefs	Cultural scenario responses
7	Definition of Success	Resource allocation games
8	Coping Mechanisms	Stress-simulation choices
9	Natural Strengths	Pattern recognition tests
10	Cognitive Drains	Attention & memory fatigue
11	Personal Boundaries	Social scenario simulations
12	Aesthetic Identity	Visual preference games
13	Style Persona	Color, silhouette, accessory sorting



Getting Started
Prerequisites
•Node.js v18+
•MongoDB Atlas account (or local MongoDB)
•Expo Go app on your phone (for testing)
•Google Cloud project (for OAuth)
1. Clone & Install
git clone https://github.com/yourusername/selfsphere.git
cd selfsphere
2. Start the Server
cd server
cp .env.example .env        # Fill in your credentials
npm install
npm run dev                  # Runs on http://localhost:5000
3. Start the Mobile App
cd client
npm install
npx expo start
Scan the QR code with Expo Go (iOS) or Expo Go / camera (Android).



Environment Variables
Server .env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_super_secret_key
GOOGLE_CLIENT_ID=your_google_oauth_client_id
GOOGLE_CLIENT_SECRET=your_google_oauth_client_secret
OPENAI_API_KEY=your_openai_api_key
Client .env
EXPO_PUBLIC_API_URL=http://localhost:5000
EXPO_PUBLIC_GOOGLE_CLIENT_ID=your_google_oauth_client_id



Screenshots
Coming soon — Dark Mode & Feminine Mode side-by-side previews



Roadmap
•☒ Project architecture & design system
•☒ Dual-theme cinematic UI specification
•☐ Authentication (Email + Google OAuth)
•☐ Onboarding persona baseline games
•☐ Game hub with scenario engine
•☐ 13-dimension persona vector calculation
•☐ AI Twin MVP (rule-based responses)
•☐ AI Twin v2 (ML-powered with OpenAI)
•☐ Twin auto-reply integration
•☐ Social features (friend comparisons)
•☐ Scenario marketplace (user-created)
•☐ iOS & Android store release



Contributing
We welcome contributors who vibe with the vision. Whether you’re into: - Game design & narrative writing - React Native animations - AI personality modeling - Cinematic UI/UX
…we’d love to have you.
# Fork the repo
git checkout -b feature/your-feature-name
# Make your changes
git commit -m "feat: add your feature"
git push origin feature/your-feature-name
# Open a Pull Request



License
MIT License — Built with obsession by the SelfSphere team.



