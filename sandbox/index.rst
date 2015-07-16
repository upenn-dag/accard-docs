Sandbox
=======

This application dataset creates a baseline Accard patient repository. This is not intended to serve as a full-functioning application, but as an introduction to Accard; as well as a simple example of common operations, typically required of a patient repository.

.. _sandbox-access:

Requesting Access
-----------------

To access the sandbox, you must first make a request for the DAG to enable your account in the sandbox. We do not allow everyone access. Please send an email to pmacs-dag@mail.med.upenn.edu containing your PennKey and the dates on which you will be using the application. They will respond when your PennKey has been enabled, and instructions on how and where to access the sandbox will be sent along with this response.

.. note::
    The sandbox environment resets daily. All data entered, and all user accounts added on a given day will be erased each day and replaced with sample data.


Patient
-------
Example fields have been provided as an example of extra data points you may wish to collect about a patient. 

Phases
~~~~~~

* Screening - Patient is being evaluated for participation in study.
* Consented - Patient has given consent for participation.
* In Treatment - Patient is currently being treated.
* Post Treatment - Patient has completed treatment.
* Follow Up - Patient is in a follow-up cycle, post treatment.
* Archived - Patient record has been archived.


Diagnosis
---------

Example fields have been added to the application in order to facilitate testing, and to serve as examples of what kinds of data may be collected using the diagnosis object extensions.

Phases
~~~~~~

* Discovery - Not yet diagnosed, but likely; tests being run.
* Diagnosed - Diagnosed with disease.
* In Treatment - Diagnosis is currently being treated.
* Post Treatment - Diagnosis is gone, or almost gone; maintenance cylce.
* Cured - No evidence of diagnosis.

Code Groups/Codes
~~~~~~~~~~~~~~~~~

Main (main):

* Primary Diagnosis *pri*
* Secondary Diagnosis *sec*


Activities
----------
Prototypes, and corresponding fields, have been added to the application to facilitate testing, and to serve as examples of what kinds of data may be collected using the activity component.

Stress Testing
~~~~~~~~~~~~~~
Patient stress test activity, and results. This activity resource contains information about the stress test itself, as well as resulting data from the test. Simpler activities, like a stress test yield a single set of results, so it is simpler to denormalize the data, storing the results directly on the activity itself.

Generic Surgery
~~~~~~~~~~~~~~~
Generic surgery example. A combined, single surgery activity is useful when your application collects the same data on every type of surgery you perform. If you find yourself requiring complex "logic" in order to create a surgery, it's probably time to separate each into their own activity prototype.

    Surgeries typically yield pathology data, and one surgery may yield several pathology reports. These are a prime candidate for the Accard result, and future version of Accard will have this reflected in this sandbox.

Radiation
~~~~~~~~~
An extremely simple radiation activity prototype. This is another candidate for results, but you may wish to keep the results denormalized.

Chemotherapy
~~~~~~~~~~~~
An extremely simple chemotherapy activity prototype. This is another candidate for results, but you may wish to keep the results denormalized.

.. note::
    Allows collection of :ref:`drugs<sandbox-drugs>` from the :ref:`chemotherapy drugs<sandbox-drugs-chemotherapy-drugs>` drug group.


Attributes
----------
Prototypes, and corresponding fields, have been added to the application to facilitate testing, and to serve as examples of what kinds of data may be collected using the attribute component.

Entrance Questionnaire
~~~~~~~~~~~~~~~~~~~~~~
A simple questionnaire example. This could be a larger list of questions, and could be a resource that is accepted multiple times during a patient's life.

.. note::
    This attribute contains a "comment" field. While these fields aren't necessarily "good" for your data, they can provide an easy way to leave information about a record in an easily retrievable place.

Family Medical History
~~~~~~~~~~~~~~~~~~~~~~
An attribute resource dedicated to collecting data about the patients' family members history of disease. This example contains a default implementation, which accomodates one family member per attribute. To collect data about many family members, you would simply create multiple attributes.


Behaviors
---------
Prototypes, and corresponding fields, have been added to the application to facilitate testing, and to serve as examples of what kinds of data may be collected using the behavior component.

Occupation
~~~~~~~~~~
This occupational history example contains fields relevant to discern if a patients' occupation has had anything to do with the course of their disease. This is a very simple example, yet it perfectly illustrates the type of information relevant to a behavior resource.

Drug Use
~~~~~~~~
Drug use history follows the same idea as occupational history. If the patient has done drugs; perhaps that drug use has contributed to the state of their disease.

.. _sandbox-drugs:

Drugs
-----
A few fictional, sample drugs have been provided.

.. _sandbox-drugs-chemotherapy-drugs:

Chemotherapy Drugs:

* Chemotherapy 1
* Chemotherapy 2
* Chemotherapy 3


Regimens
--------

Stressful Surgery Analysis
~~~~~~~~~~~~~~~~~~~~~~~~~~
Combines two activities, allowing you to determine the effect of stress testing leading up to, and after surgery.

**Allowed drugs**:

* None

**Allowed activities**:

* Stress Testing
* Generic Surgery

Combination Radiation & Chemotherapy
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Combines radiation and chemotherapy into groups for easy access to data within one "round" of treatment. This regimen is used in an abstract sense, as it is not necessarily an actual regimen in the normal sense; it simply gives you easy access to your data by grouping common sets of activity data.

**Allowed drugs**:

* None

**Allowed activities**:

* Radiation
* Chemotherapy

Chemotherapy Regimen
~~~~~~~~~~~~~~~~~~~~
A demonstration of denormalization of data by design allowed a drug collection directly on a regimen. There are times where you do not wish to collect data about each individual activity, just the outcome of a group of activities. This is supported by allowing regimens to collect data that would normally be captured within individual activities.

.. tip::
    When collecting data directly on a regimen, be sure that you're not attempting to collect data better suited to be collected on an activity. This creates massive data inconsistencies in the long term.

**Allowed drugs**:

* Chemotherapy Drugs

**Allowed activities**:

* None

Samples
-------

.. note::
    This section is not complete, and does not represent anything. More to follow. Support for sample collection objects has been included within the database, but is not yet part of the main interface.


Prototypes, and corresponding fields, have been added to the application to facilitate testing, and to serve as examples of what kinds of data may be collected using the sample component.

Whole Blood
~~~~~~~~~~~

DNA
~~~


