# AnchorCloud ⚓

**AnchorCloud** is an unofficial, browser-based AZ-900 study notebook designed to make Microsoft Azure fundamentals revision practical, focused, and memorable.

It combines short practice questions, exam-focused explanations, service comparisons, local examples, progress tracking, and a community leaderboard in one lightweight learning experience.

> **Important:** AnchorCloud is an independent learner project. It is not affiliated with, sponsored by, or endorsed by Microsoft.

## Features

- **Guided learning path**
  - Work through structured AZ-900 lessons.
  - Complete each lesson with at least 80% to unlock the next one.
  - Earn XP and stars as you improve.

- **Practice questions**
  - Review cloud concepts, Azure architecture and services, and management and governance.
  - Use smart mix mode to prioritize weaker topics.
  - Highlight clue phrases that help identify the correct answer.

- **Redo pile**
  - Missed questions are collected automatically.
  - Drill the questions you need to revisit most.
  - Clear a question after answering it correctly twice in a row.

- **Look-alike service comparisons**
  - Practise common AZ-900 distinctions such as:
    - VNet peering and service endpoints
    - Availability sets and availability zones
    - Service Health and Azure Advisor
    - Azure Policy and resource locks
    - VPN Gateway and ExpressRoute

- **Local explanations**
  - Explore Azure concepts using examples based on Nairobi roads and estates, M-Pesa agents, or Sheng.
  - Copy the underlying tutoring prompt for further study.

- **Readiness dashboard**
  - View weighted readiness across the main AZ-900 skill areas.
  - Create a countdown plan based on your exam date, study hours, and weakest area.

- **Optional account and leaderboard features**
  - Create an account or sign in with Supabase Authentication.
  - Save a nickname, city, and readiness score.
  - View the shared #1MillionDevs leaderboard.
  - Ask the community for explanations using familiar examples.

- **Accessible, responsive interface**
  - Works on desktop and mobile screens.
  - Includes light and dark themes.
  - Supports reduced-motion preferences.
  - Uses visible keyboard focus states and semantic labels for key controls.

## Demo

The application can be deployed as a static site using GitHub Pages or another static hosting provider.

For local development, open `index.html` in a browser or serve the repository with a local HTTP server.

## Getting started

### Prerequisites

- A modern web browser
- Optional: a local static HTTP server for development
- Optional: a Supabase project for authentication, leaderboard, and community features

### Run locally

Clone the repository:

```bash
git clone https://github.com/EstherWare/anchorcloud-az900.git
cd anchorcloud-az900
```

Start a local server. For example, with Python:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/
```

You can also open `index.html` directly, although some browser security restrictions may affect network requests when using the `file://` protocol.

## Supabase configuration

AnchorCloud uses Supabase for optional cloud-backed features:

- Email/password authentication
- Leaderboard records
- Community questions and answers

The browser client should use only a public Supabase **anonymous key**. Never place a Supabase service-role key or any other privileged secret in client-side code.

If you configure your own Supabase project, update the public project URL and anonymous key in `index.html`, then configure the following in the Supabase dashboard:

1. Enable Email authentication.
2. Configure the project **Site URL** to match the deployed application URL.
3. Add the deployed URL to the allowed redirect URLs.
4. Create and secure the tables required by the application.
5. Enable Row Level Security and add policies appropriate for your use case.

For local development, include the local origin in the allowed redirect URLs, for example:

```text
http://localhost:8000/
```

Email confirmation settings may require a new user to confirm their email address before signing in.

## Deployment with GitHub Pages

1. Push the repository to GitHub.
2. Open **Settings → Pages**.
3. Select **Deploy from a branch**.
4. Choose the `main` branch and the repository root.
5. Save the configuration.
6. Add the resulting GitHub Pages URL to Supabase's allowed redirect URLs if authentication is enabled.

Because the project is a static HTML application, no build step is required.

## Project structure

```text
.
├── index.html    # Application markup, styles, quiz data, and client-side logic
└── README.md     # Project documentation
```

## Technology

- HTML5
- CSS3
- Vanilla JavaScript
- Supabase Auth and REST APIs
- Google Fonts:
  - Bricolage Grotesque
  - Atkinson Hyperlegible
  - Caveat

The project intentionally avoids a frontend framework and build tool so that it remains easy to inspect, run, and deploy.

## Data and privacy

Local study progress is stored in the browser using `localStorage`. If you use the account and leaderboard features, selected profile and readiness information is sent to the configured Supabase project.

Do not enter sensitive personal information into the nickname, city, or community-question fields. Review and adapt the Supabase Row Level Security policies before using the project in a production environment.

## Content scope

The practice content is intended for AZ-900 revision and focuses on foundational topics including:

- Cloud concepts and benefits
- Cloud service models and pricing
- Azure regions, availability, storage, networking, compute, and identity services
- Security, governance, compliance, monitoring, and cost management

The questions are study aids, not a replacement for Microsoft's current official exam skills outline, documentation, or practice assessment. Azure services and exam objectives can change, so learners should verify important details against current Microsoft Learn material.

## Contributing

Contributions are welcome, especially improvements to:

- Question accuracy and explanations
- Accessibility and keyboard navigation
- Mobile usability
- Localized examples
- Error handling and Supabase integration
- Documentation and deployment guidance

Before opening a pull request:

1. Test the application in a modern browser.
2. Check both light and dark themes.
3. Test the relevant flow while signed out and signed in.
4. Confirm that changes do not expose private credentials.
5. Keep the application usable without optional Supabase services where possible.

## License

No license has currently been declared for this repository. Unless a license is added, the repository owner retains all rights to the source code. Contact the repository owner before redistributing or reusing the project beyond normal GitHub viewing and contribution workflows.

## Acknowledgements

- Microsoft Azure and Microsoft Learn for the AZ-900 learning ecosystem.
- The #1MillionDevs community and hackathon context that inspired this project.
- Learners and contributors who help make cloud concepts easier to understand through relatable examples.
