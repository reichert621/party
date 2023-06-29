# party

This will be a lightweight open-source alternative to Partiful and Facebook Events. At a high level, this app will allow people to create events, invite their friends to RSVP, and send out reminders about the events. It should be extremely easy to use, and should not require a Facebook/Google/etc account. Like Partiful, a phone number should be good enough.

### What problem does this solve?

Creating and planning events with friends can require a lot of logistics and coordination, especially as more people are invited. The Facebook Events product is pretty good at solving this, but requires people to be active on Facebook (which fewer people are these days). Partiful solves this by only requiring a phone number to RSVP, which is the approach that we will take here.

It could also solve the problem of decision-making when it comes to where and when people want to meet, through some sort of polling or voting mechanism. This is how my friends and I currently solve this problem: we create a new chat group in Facebook Messenger with the event title as the group title, and use the built-in polling feature to vote on the best places and times to meet.

### Goals

- As an event planner, I can create an event with a title, description, time, and place
- As an event planner, I can send my event URL to the people I want to invite, and they can view it and RSVP using their phone number
- As an event planner, I can edit or delete events that I have created
- As a user, I can view events my friends have invited me to
- As a user, I can RSVP for events using my phone number
- As a user, I can leave comments on events
- As a user or event planner, I can create an account with my phone number

### Technical breakdown

I will likely build this out using a React/NextJS/TypeScript frontend, and either [Firebase](https://firebase.google.com/) or [Supabase](https://supabase.com/) for my backend. I could roll my own backend with [Prisma](https://www.prisma.io/) and PostgreSQL, but I would rather set up a proof of concept first with something that can handle auth and storage for me right out of the gate.

I know that Partiful uses Firebase, but given the fact that a lot of my data models will be relational (i.e. `events` belong to `users`, `events` can have many `invites` and `comma), this might be a good opportunity to give Supabase a shot.

I imagine if I want to send event reminders via SMS, I may need to use [Twilio](https://www.twilio.com/en-us) as well.

It will be important to make sure that the UI is optimized for mobile responsiveness as well, since I imagine most people will want to be able to use this on their phones.
