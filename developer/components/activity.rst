Activity
========

Activities, by far, are the largest resource Accard offers. They represent any
and all actions that can be taken by, for, or to a patient. Almost everyhing
you think of, in some way, could be classified as an activity. The Accard
standard definition for an action is "A resource, marked by a date that may or
has been done to, for or by a patient".

Activities may be connected to a patient or a patient/diagnosis. The difference
being; when an activity is being done is it in search of, or in response to, a
diagnosis? If yes, you will typically want to require a diagnosis be present.
Otherwise, you may simply connect it to the patient resource only.

.. note::
    Activities, in the future, will be able to spawn child resources known as
    "results". Results are meant to contain the information resulting of a
    given activity. Some activities may yield multiple "results", hence the
    reason for a new Accard resource. *For the time being, results are to be
    stored directly on the activity resource itself*.

.. note::
    Drugs may, optionally, utilize the drug resource library.
