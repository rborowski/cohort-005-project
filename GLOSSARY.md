# Cadence

An online course platform where students buy courses and instructors teach them.

## Language

**Student**:
A person who buys and takes courses.
_Avoid_: Learner, user, customer

### Refunds

**Refund Request**:
A student's ask to get their money back for a course they bought. A purchase can have at most one Refund Request. Approving it cancels the purchase and the student loses access to the course.
_Avoid_: Chargeback, Reversal, Cancellation, cancellation request

**Refund**:
The money owed back to a student, which exists from the moment their Refund Request is approved. It is always exactly the Refund Amount and has no status of its own.
_Avoid_: Reversal, Chargeback, partial refund

**Pending**:
The status of a Refund Request that nobody has decided on yet.
_Avoid_: Requested, Open, Raised

**Approved**:
The status of a Refund Request that has been accepted, which means a Refund is owed.

**Declined**:
The final status of a Refund Request that has been turned down. No Refund is owed, and the student cannot make another Refund Request for that purchase.
_Avoid_: Rejected, Denied

**Refund Window**:
The 14 calendar days after a purchase. A student can only make a Refund Request during this time.
_Avoid_: Cancel window, cancellation period

**Refund Eligibility**:
The rules that decide whether a student can make a Refund Request. They must be inside the Refund Window, have watched less than 2 hours, have completed less than half the lessons, and not be holding a claimed team seat.
_Avoid_: Cancellation offer

**Refund Amount**:
The amount a Refund would send back. It is always what the student actually paid for the purchase.
_Avoid_: Refundable amount, list price

## Example dialogue

> **Dev:** "Priya's refund is pending."
> **Domain expert:** "Her **Refund Request** is **Pending**. There's no **Refund** until it's **Approved**."
>
> **Dev:** "Tom's refund got declined, can he try again?"
> **Domain expert:** "His **Refund Request** was **Declined**, and that's final for the purchase. No **Refund** ever existed."
