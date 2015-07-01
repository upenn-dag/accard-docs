Sample Application
==================

This application dataset creates a baseline Accard patient repository. This is
not intended to serve as a full-functioning application, but as an introduction
to Accard; as well as a simple example of common operations, typically required
of a patient repository.


Patient
-------
Example fields have been provided as an example of extra data points you may
wish to collect about a patient. 

.. tip::
    Developers! Read more about :doc:`The Patient Component </developer/components/patient>`.

Fields
~~~~~~

Eye Color (choice, eye-colors):

* Black
* Blue
* Brown
* Hazel
* Green

Last Contact (date)

Phases
~~~~~~

* Screening
* Consented
* In Treatment
* Post Treatment
* Follow Up
* Archived



Diagnosis
---------

Example fields have been added to the application in order to facilitate
testing, and to serve as examples of what kinds of data may be collected using
the diagnosis object extensions.

.. tip::
    Developers! Read more about :doc:`The Diagnosis Component</developer/components/diagnosis>`.

Fields
~~~~~~

Diagnosed Elsewhere (checkboxbox)

Phases
~~~~~~

* Discovery
* Diagnosed
* In Treatment
* Post Treatment
* Cured

Code Groups/Codes
~~~~~~~~~~~~~~~~~

Main (main):

* Primary Diagnosis *pri*
* Secondary Diagnosis *sec*


Activities
----------
Prototypes, and corresponding fields, have been added to the application to
facilitate testing, and to serve as examples of what kinds of data may be
collected using the activity component.

.. tip::
    Developers! Read more about :doc:`The Activity Component</developer/components/activity>`.

Stress Testing
~~~~~~~~~~~~~~
Patient stress test activity, and results. This activity resource contains
information about the stress test itself, as well as resulting data from the
test. Simpler activities, like a stress test yield a single set of results, so
it is simpler to denormalize the data, storing the results directly on the
activity itself.

Patient Able to Perform (checkbox)

Method (choice):

* Treadmill
* Stairs
* Jumping Jacks

Duration (number)

Results (choice):

* Poor
* Average
* Good
* Excellent

Comments (text)

Generic Surgery
~~~~~~~~~~~~~~~
Generic surgery example. A combined, single surgery activity is useful when
your application collects the same data on every type of surgery you perform.
If you find yourself requiring complex "logic" in order to create a surgery,
it's probably time to separate each into their own activity prototype.

    Surgeries typically yield pathology data, and one surgery may yield several
    pathology reports. These are a prime candidate for the Accard result, and
    future version of Accard will have this reflected in this sample application.

Surgeon (choice):

* Dr. Patel, MD.
* Dr. Schmitt, MD.
* Dr. Constantine, MD.

Surgery Procedure (choice):

* Procedure 1
* Procedure 2
* Procedure 3

Site (choice) [#f1]_:

* Head
* Neck
* Shoulder
* Chest
* Abdomen

Method (choice):

* Method 1
* Method 2

Comments

Radiation
~~~~~~~~~
An extremely simple radiation activity prototype. This is another candidate
for results, but you may wish to keep the results denormalized.

Type (choice):

* Proton
* Photon

Site (choice) [#f1]_:

* Head
* Neck
* Shoulder
* Chest
* Abdomen

Grays (number)

Chemotherapy
~~~~~~~~~~~~
An extremely simple chemotherapy activity prototype. This is another candidate
for results, but you may wish to keep the results denormalized.

.. note::
    Allows collection of :ref:`drugs<sample-application-drugs>` from the :ref:`chemotherapy drugs<sample-application-drugs-chemotherapy-drugs>` drug group.

Dose (number)

Route (choice):

* IV
* Oral


Attributes
----------
Prototypes, and corresponding fields, have been added to the application to
facilitate testing, and to serve as examples of what kinds of data may be
collected using the attribute component.

.. tip::
    Developers! Read more about :doc:`The Attribute Component</developer/components/attribute>`.

Entrance Questionnaire
~~~~~~~~~~~~~~~~~~~~~~
A simple questionnaire example. This could be a larger list of questions, and
could be a resource that is accepted multiple times during a patient's life.

Symptom Location (choice, body-locations) [#f1]_:

* Head
* Neck
* Shoulder
* Chest
* Abdomen

Symptom Severity (choice, symptom-severities):

* Not Severe
* Severe
* Very Severe
* I Don't Know

Family Medical History
~~~~~~~~~~~~~~~~~~~~~~
An attribute resource dedicated to collecting data about the patients' family
members history of disease. This example contains a default implementation,
which accomodates one family member per attribute. To collect data about many
family members, you would simply create multiple attributes.

.. note::
    This attribute contains a "comment" field. While these fields aren't
    necessarily "good" for your data, they can provide an easy way to leave
    information about a record in an easily retrievable place.

Family Member (choice, family-members):

* Mother
* Father
* Brother
* Sister
* Aunt
* Uncle
* Grandmother
* Grandfather

Side of Family (choice, family-sides):

* Maternal
* Paternal

Diseases (choice, relevant-diseases, addable):

* Diabetis
* Heart Attack
* High Blood Pressure

Comments (text)


Behaviors
---------
Prototypes, and corresponding fields, have been added to the application to
facilitate testing, and to serve as examples of what kinds of data may be
collected using the behavior component.

.. tip::
    Developers! Read more about :doc:`The Behavior Component</developer/components/behavior>`.

Occupation
~~~~~~~~~~
This occupational history example contains fields relevant to discern if a
patients' occupation has had anything to do with the course of their disease.
This is a very simple example, yet it perfectly illustrates the type of
information relevant to a behavior resource.

Industry (choice, industies):

* Automobile
* Chemical
* Construction
* Energy
* Financial
* Healthcare
* Industrial
* Infrastructure
* Metal
* Retail
* Technology
* Textile
* Transportation
* Travel

Handled Hazardous Materials (checkboxbox)

Drug Use
~~~~~~~~
Drug use history follows the same idea as occupational history. If the patient
has done drugs; perhaps that drug use has contributed to the state of their
disease.

Drug Type (choice, drug-types):

* Alcohol
* Amphetamines
* Cannabis
* Cocaine
* Crack Cocaine
* Ecstasy
* Heroin
* Inhalants
* Ketamine
* LSD
* Mushrooms
* Methanphetamine
* PCP

Frequency (choice, frequencies):

* Hourly
* Daily
* Weekly
* Bi-Weekly
* Monthly
* Occasional


.. _sample-application-drugs:

Drugs
-----
A few fictional, sample drugs have been provided.

.. tip::
    Developers! Read more about :doc:`The Drug Component </developer/components/drug>`.

.. _sample-application-drugs-chemotherapy-drugs:

Chemotherapy Drugs:

* Chemotherapy 1
* Chemotherapy 2
* Chemotherapy 3


Regimens
--------

Samples
-------

.. note::
    This section is not complete, and does not represent anything. More
    to follow. Support for sample collection objects has been included within
    the database, but is not yet part of the main interface.

Prototypes, and corresponding fields, have been added to the application to
facilitate testing, and to serve as examples of what kinds of data may be
collected using the sample component.

.. tip::
    Developers! Read more about :doc:`The Sample Component</developer/components/sample>`.

Whole Blood
~~~~~~~~~~~

DNA
~~~

.. tip::
    Developers! Read more about :doc:`The Regimen Component</developer/components/regimen>`.





.. rubric:: Footnotes

.. [#f1] The body locations list is used in multiple places, use caution when
         editing this option.

