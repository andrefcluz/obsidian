---
created: 2025-10-18T09:07
updated: 2025-10-21T18:47
tags:
  - endurpal
---
# 🗃️ Description

Name: EndurPal, CalEndur
Website: endurpal.com 



Slogan (to choose):
- Endurance training, made easy.
- Powerful training, made easy/simple.
- Advanced training, made easy/simple.
- Complex training, made easy/simple.
- Endurance, simplified.
- Advanced training, simplified.
- Train smart. Go farther.
- Stronger. Smarter. Simpler.

---

# 🎯 Features

## 🏃 Workouts
- User specific settings
	- Basic user data (sex, birthdate, country, city, etc)
	- Units (Metric/Imperial, Celsius/Fahrenheit)
	- Define training zones. Old zones will kept, deactivated. Then we using heart rate zones in a workout, the zones active in that moment will be used.
		- Heart Rate zones
		- Pace zones
	- Workout types (per sport)
		- Create types with any naming (Easy, Intervals, etc)
		- Use different colors for each type
		- Bundle workouts
			- Auto add specific workouts together with the ones of that type. Example: Create a type called "Intervals" and set, when a workout from this type is added to the calendar, the workout "Warmup" will also added automatically before, and the workout "Cooldown" will be added automatically after the main workout
			- Option to choose between integrating the bundle workouts inside the main one, or as separated workouts
- Workouts
	- Fields
		- Workout sport
		- Workout name
		- Workout type
		- Workout description/notes
		- Color
		- Steps
		- Workouts bundle
	- Color picker. By default uses the workout type color, but can be changed
	- Steps types
		- Step
			- Type: Run, Rest, Recover, Warmup, Cooldown, Other
			- Duration
				- Duration: HhMMmSSs
				- Distance: X km/m/mi
				- Lap Button Press
			- Intensity
				- Pace Zone (EndurPal): One of the pace zones defined in EndurPal
				- Pace Interval: Min Pace - Max Pace (min/km or min/mi)
				- HR Zone (Device): Z1, Z2, Z3, Z4 or Z5
				- HR Zone (EndurPal): One of the HR zones defined in EndurPal
				- HR Interval: Min HR - Max HR
				- Cadence Interval: Min Cadence - Max Cadence
		- Repeat
			- Option to skip the last step of the repeat if it's a Recover or Rest
	- The steps can be added using 3 different methods
		- Manually (using a dedicated interface, similar to Garmin's)
		- Typed (using internal structure, similar to intervals.icu)
		- AI prompt (the user describes the workout and the AI will add all the steps automatically)
	- Bundle workout to that specific workout, just like in the workout types. This will have priority over what's defined in the workout type
	- Auto calculate duration and distance for the entire workout
	- Options
		- Create, Edit, Delete
		- Archive, Unarchive
		- Duplicate
		- Add to calendar
			- Add to specific date
			- Repeat
				- Select days of the week
				- Number of weeks to repeat or repeat until specific date 
		- Add to plan
			- Add to specific plan day (week number+weekday)
			- Repeat
				- Select days of the week
				- Number of weeks to repeat or end of plan
		- Share (file, link or share directly with other users)

## 📆 Calendar
- Entry types
	- Workout
	- Activity
	- Event (Race)
	- Goal
	- Health Status
	- Note
- If a training plan is in progress, there will be some visual indication around the calendar, between the plan start and end dates. The same will happen for blocks inside the plan
- Clicking on a specific date, will give the option to create any entry type (except activity, their are pulled from external services) and training plans (which always starts on a Monday and ends on a Sunday)
- The workouts and training plans library will be shown next to the calendar, and both workouts and plans can be drag and dropped in any date of the calendar
- Entries can be moved around in the calendar (except activities and workouts added by a coach)
- A week can be "added", moving every workout (except coach workouts) one week further (think about how to do this when following a plan that ends in a race, in this case shouldn't be possible the move the entire plan). Same think for removing, moving every workout one week back.
- ...

## 👟 Activities
- Pull activities from external services (Garmin, Strava, Coros, etc) and all the available data
- Activities can be modified
	- Activity name
	- Sport (Run, Cycling, Swimming, etc)
	- Sub-sport (Trail Run, Treadmill, MTB, Open Waters Swim, etc)
	- Activity type (Workout, Long Run, Race)
	- Visibility (public or private)
	- Show/hide in feed (if the visibility is set to public)
- The athlete can add
	- Description (public)
	- Personal notes (private)
	- Self evaluation (private + coach)
	- Perceived effort (private + coach)
	- Gear used (public or private)
- Other athletes can comment (if the activity is visible to public)

## 📋Training Plans
- Training plans always start in a Monday and end in a Sunday, and need to have at least 2 weeks
- They can be divided in blocks, which can be named and a color
- ...

## 📈 Statistics & Analytics 
- Basic
	- Totals (week, month, plan, year)
	- ...
- Advanced - Premium Athletes
	- ...

## 🛒 Plans Marketplace
- Seller
	- Can sell individual training plans (the same plan can contain multiple variations)
	- Can sell training plans bundles
	- Can update existing training plans
	- Gets 80% of the sell value (EndurPal keeps 25%)
	- Can offer discounts (like in Black Friday, Christmas, etc)
	- Can offer plans for free or with a special discount to specific athletes of their choice
	- Gets an overall rating based on the rating of their plans
- Buyer
	- Can purchase individual training plans (including all variations) 
	- Can purchase training plans bundles
	- Gets updates for owned plans for free
	- Can rating and review owned plans
	- Premium athletes have 10% off in all plans/bundles (cut from the EndurPal part)

## 🗣️ Chat/Messaging
- See and exchange messages with any user who has chat active
- Exchange messages with any coach
- Get notifications/badges for new messages

## 🧠 Coaching
- Can add any athlete to his team
- Can create workouts and training plans, and add them to his athlete's calendars
	- When adding training plans, has the option to let the athlete see the entire plan in their calendar right away, or release the workouts in a weekly basis (in a set weekday and time)
- Can modify his athlete's workouts (that they added, can't modify workouts added by the athlete himself)
- Has access to his athletes activities, stats, events, goals and health status,from the date the athlete was added to the team)
- Can comment on his athletes activities, weeks, training blocks, training plans, events and health status
- Can message his athletes

## 🤓 AI Assistant
- Can create training plans
- Can analyse current form, fatigue, etc and provide insights and suggest workout adjustments for the following days
- Can analyse individual workouts and provide insights

## 🛠️ Extra Tools
- Activities toolkit
	- Auto-renaming activities - Rename activities automatically in EndurPal and supporting external services (Strava, Garmin, etc), based on rules (check ActivityFix)
		- Example "#143/26 - E - 8km" - activity counter, followed by the training type, and the distance/duration
	- Add activity data to the description/notes - weather detail, metrics, etc
	- Automatically make some type of activities private/hidden from feed
- Social Platform
	- Feed
	- User profile 
		- Activity sharing
		- Year activity graph (similar to GitHub's contribution graph and Tapistree)
	- Follow other users and their activities will appear in the feed

## ❎ Feature Requests & Voting
- Athletes have credits they can use to request new features or improvements, and to vote on the ones already posted by other users
- Credits
	- Free athletes have 5 credits per week to spend
	- Premium athletes and coaches have 15 credits per week to spend
	- Making a new request costs 5 credits
	- Vote in a request costs 1 credit
- Credits don't accumulate, they reset every Monday. Unspent credit are lost.
- After x number of votes, the features is approved, and is moved to the roadmap backlog (Trello), to be implemented in the future
- Requests can be merged, if the idea is the same, and the votes are added together


---
# 🙍 User Types
The same user can be an Athlete and a Coach. Both can be used simultaneous, and have separate sections, each with specific features (some unique, others in common).
## 🏃‍♀️ Athlete
### Free Athlete
Cost: Free
Perks:
- Workouts
- Calendar
- Activities
- Statistics & Analytics (Basic Features)
- Training Plans
- Plans Marketplace
- Chat/Messaging
- Coaching
- Extra Tools
- Feature request & voting (low number of votes)
### Premium/Plus Athlete
Cost: 5€/month, 50€/year
Perks:
- Everything in Free
- Statistics & Analytics (Advanced Features)
- AI Assistant
- Feature request & voting (higher number of votes)
- 10% off in plans purchases
- Support further development

## 🧠 Coach
Cost: 10€/month (includes 5 athletes) + 2€/month per additional athlete
Perks:
- Add athletes to his team
- Add plans and individual workouts to his athlete's calendar
- Modify his athlete's workouts (that they added, can't modify workouts added by the athlete himself)
- Check his athlete's activities, statistics and events
- Give feedback for activities, weeks, training blocks, training plans, events, goals and health status


---

# 📅 Roadmap

### Phase 0 - Research & Planning [[EndurPal - Roadmap - Phase 0 - Research and Planning|→]]
- Pick full stack ✅
- Define core features ✅
- Build a UI/UX mockup draft
### Phase 1 - MVP - Calendar, Workout Builder & Garmin Integration (Push Workouts) [[|→]]
- Authentication
- User and training basic settings
- Create workouts
- Show a calendar
- Add and remove workouts from the calendar
- Bug reporting
- Send planned workout to Garmin
### Phase 2 - Pull Activities Data from Garmin [[|→]]
- Get activities from Garmin and show them in EndurPal
### Phase 3 - Training Plans Builder [[|→]]
- Create personal training plans
- Add training plans to calendar
### Phase 4 - Training Plans Marketplace [[|→]]
- Market to buy and sell training plans
### Phase 5 - Integration with more brands (Coros, Suunto, etc) [[|→]]
- Provide more brands (to send workout to and to pull data from)
### Phase 6 - Detailed statistics & analytics [[|→]]
- Detailed statistics/graphics for activities, weeks, current form, etc
### Phase 7 - Chat/Messaging [[|→]]
- Messaging feature, so users can chat with each other, specially coaches and their athletes
### Phase 8 - Coaching [[|→]]
- Coach other users (manage their workouts calendar, see activities, provide feedback, etc)
### Phase 9 -  More sports (cycling, swimming, triathlon, etc) [[|→]]
- Add more sports and sub-sports
### Phase 10 - Extra Tools - Activities Updater (Smart Naming, privacy etc) [[|→]]
- Modify activities automatically in EndurPal and external services (name, description, privacy, etc)
### Phase 11 - AI assistant (create running plan, workouts and form analysis, etc) [[|→]]
- AI assistant to create running plans and workout, provide feedback for activities and current form, etc 
### Phase 12 - Feature Request & Vote System Platform [[|→]]
- Platform to request new features with a voting system 
### Phase 13 - Android App [[|→]]
- EndurPal Android app
### Phase 14 - iPhone App [[|→]]
- EndurPal iPhone app

---

# 💬 Topics to Explore

- Logo design: https://chatgpt.com/g/g-p-68ef15fb23ec8191bc39f1def07d12ec-endurpal-calendur/c/68f5d05e-e54c-8328-9407-9f4d4c8f7137
- UI/UX Templates: https://chatgpt.com/g/g-p-68ef15fb23ec8191bc39f1def07d12ec/c/68f37a04-5598-832b-b3a5-abe30a2cc48d
- Workout builder: https://chatgpt.com/g/g-p-68ef15fb23ec8191bc39f1def07d12ec/c/68f3c335-e3f8-832f-96c5-9ebf39dad007
- Multiple languages: https://chatgpt.com/g/g-p-68ef15fb23ec8191bc39f1def07d12ec-endurpal-calendur/c/68f37d52-d708-8331-9110-94b833f05f21
- Early-stage bug report system: https://chatgpt.com/g/g-p-68ef15fb23ec8191bc39f1def07d12ec-endurpal-calendur/c/68f5589b-e988-832a-8d9a-ba8c5cfb677c


