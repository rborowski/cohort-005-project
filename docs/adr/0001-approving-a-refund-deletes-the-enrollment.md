# Approving a Refund Request deletes the enrollment

When a Platform Admin approves a Refund Request, the learner loses access to the course straight away, and we do that by deleting their enrollment row rather than marking it as ended. Every access check in the app already treats "an enrollment exists" as "may view the course", so deleting keeps all of them correct without teaching about eight separate queries to ignore ended rows. The history an ended row would have kept already lives elsewhere: the purchase, the Approved Refund Request, and the learner's lesson progress and watch events, which we deliberately keep.

## Consequences

- If the learner buys the course again, they get a fresh enrollment with a new `enrolledAt`, and their old progress shows up again because progress belongs to the learner and the lesson, not to the enrollment.
- Lists of a course's students (e.g. the instructor's students page) stop showing a refunded learner, with no record that they were ever enrolled.
- Watched time counts every watch event the learner has ever made, across all purchases. If they buy again, their earlier viewing still counts towards the 2-hour cap. That doesn't matter today, because a second Refund on the same course isn't allowed.
