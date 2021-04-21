This fine will contain all the design considerations of project SimpleDating.

**Estimated usage patterns:**

* average 10 paginated reads per user per day (each page contains 10 user profiles)
  - 6 images (5MB maximum size) + Biographical Info + MetaData = 30 MB
* average 5 profile update per user per day
  - each update contains 1 image write (5MB max)
  - each update contains 1 bio update (1kB write)
* average 100 profile ratings (1kB) per user per day
* average 5 messages (1kB write) per day
* average 5 profile feedbacks (1kb write) per day
* No idea what logging write load looks like yet
* Average 25 matches per user (50% * 50% * 100 profile views per day) per day
  - each match stored in 256B
  - on average 6.4kB of match info generated per user per day

* Users
  - 20% of all users are active at any given moment
  - Expecting 10k active users simultaneously
  - Maybe up to 100k active users simultaneously if we push it
  - 1M simultaneous users?? Nah not worth considering at this point.

Total data storage required:

Images: 30MB * 100k users * 5 = 15TB total

User Biographical Profile Data: 1kB * 100k users * 5 = 500MB total

User Match Data: 6.4kB * 100k users = 640MB per day

User Message Data: 5kB * 100k users = 500MB per day

User Profile Review Data: 5kB * 100k users = 500MB per day


Generating 1.64 GB of user data each day. 600GB generated each year, which is 3TB over 5 years.

Read and Write Load:

1.64GB of database write per day, which is around 20kB of read per second. Assuming peak app write 
volume is 10x the average volume, that's 200kB/s of write volume

3GB of image read per user per day, which is about 40GB/s of read volume for images
105kB of text read per user per day, which is about 120kB/s of read volume for biographical info

Not sure which existing database technologies are best suited for my needs.

___To Be Continued___

Next Steps:
Designing Application Data Model
Designing the Application Data Store Architecture
Reading "Design Data Intensive Applications" by Kleppmann
