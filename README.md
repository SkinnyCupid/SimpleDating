# SimpleDating
Open-source, free-to-use, non-profit dating application. 

About SimpleDating:

1. Intended as a practice to building my first real-world application with real users. I will, however, strive for high application performance and good user experience.
2. Intended users are adults in US/Canada who are looking for long-term/short-term relationships.
3. Goal is to match people quickly so they are off the platform living happily elsewhere. Maximizing total satisfied users instead of total active users.
4. Maintenance will rely on periodic donations if there are actual users.
5. I am inexperienced when it comes to designing data-intensive applications or working with large codebases collaboratively. In fact, I have zero industry experience and no one wants to hire me right now. Any feedback on my design and any code review is GREATLY appreciated.
6. There will be absolutely no monetization of user data at any point. Everything collected is strictly for matching purposes only and will be kept completely confidential.


System Design
 
Core required features:
1. Application runs on all modern browsers, iOS and Android platforms.
2. Registration/Login with Email or Facebook/Google accounts.
3. User can create/update/delete a profile.
4. Monthly donation goal / built-in payment system to cover maintenance cost.
5. Users are required to rate every profile they viewed before proceeding to the next profile.
  - Currently looking at a simple 1 - 10 star system, or alternative a 5 star system for different criterias.
  - Optional anonymous feedback can be given to each profile when a user views that profile
  - The goal is to create a positive community that enables other users to improve.
  - Ratings resets monthly to allow people improve their profile.
6. Backend algorithm selects profiles for each user based on location and rating difference.
  - Users will see other active users' profiles within a reasonable radius. (25 miles???)
  - A user rated as 7.3 star on average will get be shown to other users in the 6.1 - 8.5 range.
  - A "match" is defined as when bidirectional messeaging from both users is enabled.
  - Currently no plan to integrate ML models for matching.
7. User can ignore another account to never see it again.
  - A maximum of 3 ignores is provided weekly.
  - User can also unignore anyone at any moment.
8. User can receive messages from other users, whom the user rated in their top 50% percentile.
  - User will receive notification if he/she is rated in the top 50 percentile by someone else.
  - When both users are in each other's top 50 percentile, a "match" occurs
  - Each user is limited to 5 unreciprocated messages a day. Reciprocated messages have no such limits
  - The purpose of message throttling is to not overwhelm people with 100+ messages
  - Each user can unmatch/ignore another user at any given moment.

Other nice-to-haves:

9. Community experience.
  - Mechanism needed to detect and ban bots/catfishing accounts when there's enough users.
  - Mechanism to detect and flag self-promotional accounts.
  - Mechanism to identify unsuccessful users and advise them to not waste time on the app.
  - Mechanism to report abusive/uncivil actitivities. Repeat offenders are banned.
10. Metrics collection for monitoring/analytics.


This is also a project where I want to integrate unit testing, agile development workflow, CD/CI into the development process, since nobody was willing to hire me and teach me how to do things the proper way, I'll have to learn everything on my own :(

Tech Stack:
(Any suggestions are EXTREMELY welcomed. Please include any critique of my tech choices, alternatives with rationales to help me better understand what I need to do!)

For Frontend, currently looking at:
  - JavaScript ES6+,
  - React/React-native,
  - Babel,
  - Redux,
  - Webpack,
  - GraphQL
  - HTML5
  - CSS or one of its popular superset.
  - For mobile I still have to learn everything :(
For Backend, currently looking at:
  - Run everything in AWS (seems like 400$/Month is a good ballpark for 100K users)
  - EC2 or Lambda depending on how big the codebase needs to be
  - NodeJS or Python for backend scripts.
  - Postgres or DynamoDB for application data store.
  - S3 buckets for separate image store???

For CD/CI:
  - no idea exactly what to do at the moment. I am a noob
  - Maybe Gitlab or Jenkins ???
  - Logging ???

Current Team:
just me @SkinnyCupid for now, but anyone is welcome to join.

Project Timelines:
1. April 25st
- Finalize design choices and commit to a tech stack.
2. May 10th
- Complete the design diagram, identify all the application access patterns, Reads & Writes.
- Complete the design of application data model, back APIs, identify all of the managed services that I need
- Breaking the system into individual manageable and testable pieces
3. June 1st
- First Web Browser frontend static version (version 0.1.0?? what's the proper label here)
- Complete profile creation, Email registration
4. No point in planning anything further out. Items 1-3 could already be wildly inaccurate.

Might be able to work 7 hours a day on this. I believe the best way to learn system design is to actually design and build an entire system from scratch. Still applying to jobs for a few hours each day, but don't want to waste all my time writing cover letters or refreshing LinkedIn. Already solved half the problems on LeetCode so interview prep is rather pointless.
