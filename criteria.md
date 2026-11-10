# Acceptance criteria — TakeMeter

Five criteria that say what "working" means for this classifier, written in
unit 5 **before** anything was trained.

**All five are yours this time.** None are given. You've had two projects of
practice.

An acceptance criterion names a number. *"The model is accurate"* is an
opinion. *"Every label has an F1 of at least 0.60 on the held-out set"* is a
criterion.

Under each, write a sentence or two on **why that number**. A reason that says
something about your data or your taxonomy earns credit — *"I picked 0.60 F1
for `reaction` because it's my smallest label and I only have about 50
examples of it"*. A reason that could be attached to any project does not.

> Missing your own targets next unit costs you nothing. Setting a target so
> easy you can't miss it does.

---

## Pick numbers you can defend

Not numbers that sound impressive. Three labels means a coin-flip guesser gets
about 33%, so a target of 0.40 is barely a target. Your number should sit
somewhere you'd honestly call useful.

**Cover at least three of these five areas.** They're here as prompts, not as a
form to fill in — a criterion that fits none of them is fine if it names a
number.

| Area | A question it could answer |
|---|---|
| Overall accuracy | How often does it need to be right to be worth using? |
| Per-label performance | Is one label allowed to be much worse than the others? |
| Balance | How lopsided can your label counts get before it's a problem? |
| Consistency | If someone else labelled the same posts, how often should you agree? |
| Confidence | Should a confident prediction be right more often than an unsure one? |

Two things worth knowing before you pick numbers, because both will affect
whether you hit them:

- **Your smallest label will have the jumpiest score.** If a label has 50
  examples, about 8 land in the test split. An F1 computed on 8 examples moves
  a lot between seeds. A target for that label should be looser than one for
  your biggest label, and saying so is a good reason.
- **Unit 6 tests across three seeds, and the target has to hold across all
  three.** A target of 0.65 against results of 0.71, 0.62, 0.68 is a **miss**.
  Pick with that in mind — it is stricter than it first sounds.

---

## 1. Overall Accuracy

The classifier must achieve an overall accuracy of at least 0.65 (65%) on the held-out test set across all three random seeds.



**Why this target:**
I chose 0.65 because my dataset has four different categories, and I want the classifier to do better than simply choosing the most common category. Pizza making is the largest category in my available data, so I want the model to demonstrate that it can correctly classify other types of pizza-related posts too.

---

## 2. Pizza-making performance


The pizza_making category must achieve an F1 score of at least 0.60 on the held-out test set across all three random seeds.


**Why this target:**

I chose 0.60 because pizza making is the largest category in my dataset, with 80 examples in the records I reviewed. Since it has more examples than the other categories, I expect the model to have a reasonable opportunity to learn its patterns and classify these posts correctly.


---

## 3. Postive-experience performance

The positive_experience category must achieve an F1 score of at least 0.55 on the held-out test set across all three random seeds.


**Why this target:**

I chose 0.55 because positive experiences are the second-largest category in my dataset, with 57 examples in the records I reviewed. These posts include positive customer experiences, appreciation for delivery workers, and good restaurant experiences. I want the classifier to recognize these different types of positive posts.


---

## 4. Smaller-category performance

Both customer_conflict and delivery_incident must achieve an individual F1 score of at least 0.30 on the held-out test set across all three random seeds.



**Why this target:**

I chose 0.30 because these are my two smallest categories, with 19 customer conflict examples and 16 delivery incident examples in the records I reviewed. Since they have fewer examples, their F1 scores may change more between random seeds. I chose a lower target to account for the smaller number of examples while still expecting the classifier to recognize both categories.

---

## 5. Dataset balance

Each of the four categories must represent at least 8% of the complete 200-post dataset.



**Why this target:**

I chose 8% because delivery incidents are the smallest category in the records I reviewed. I want every category to have enough examples for the classifier to learn from instead of allowing one category to become too underrepresented compared with the others.


---

<!-- ─────────────────────────────────────────────────────────────────────────
     UNIT 6 — read this before you change anything above.

     If a criterion turns out to be BROKEN rather than merely unmet, you can
     revise it, and that earns credit. But never delete or edit the original
     line. Add the revision underneath, like this:

         ## 2. Every label performs acceptably

         The model performs well on all labels.

         **Why this target:** ...

         > **Revised in unit 6:** Every label has an F1 of at least 0.60 on
         > the held-out set.
         >
         > **Why revised:** "performs well" gave me nothing to check. I
         > couldn't produce a verdict from it at all.

     That's a revision because the criterion couldn't be MEASURED.

     Lowering a target because you missed it is not a revision, and it costs
     you the point:

         ✗ "Overall accuracy of at least 0.65" → "at least 0.55", because
            0.65 turned out to be optimistic for 200 examples.

     A number you missed stays where it is, gets diagnosed, and gets a fix
     attempted. That's where the points are.
     ───────────────────────────────────────────────────────────────────────── -->
