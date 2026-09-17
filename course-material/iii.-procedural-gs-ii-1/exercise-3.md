# Exercise C-2

{% hint style="warning" %}
Complete the tasks below and submit the files **by 9:45 am on Friday, November 22nd.**

File 1: Rhinoceros file

File 2: Grasshopper file (only one file for all tasks!)

File 3: PDF of the word document file with answers

Please follow the file naming convention as shown in the [**Syllabus**](../../syllabus.md#submissions).

[**Submit here**](https://moodle-app2.let.ethz.ch/course/view.php?id=23670)
{% endhint %}

{% hint style="info" %}
Use the Grasshopper file from the tutorial and the new Rhinoceros file (the one for the exercise) as a base to solve this exercise. Then, answer the questions in the docx file. You will find all these files [**here**](./#files).
{% endhint %}

### Task 1 - Add more loads

Add multiple external loads to the current algorithm.

### Task 2 - Remove "zero" loads

The current algorithm crashes when the external loads have zero magnitude. Modify the algorithm so that when an external load has zero magnitude that load is not considered during the form-finding process.

{% hint style="info" %}
Use the solution from Task 1 as a base to solve this task.
{% endhint %}

### Task 3 - Add an asymmetric load

A large group of people is crossing together the bridge. Add to the algorithm this asymmetric load and display it as if it would be moving from one anchor point to the other as shown in the video below.

{% embed url="https://vimeo.com/769584331" %}

{% hint style="info" %}
Use the solution from Task 2 as a base to solve this task.
{% endhint %}

{% hint style="success" %}
Hints:

* Define Q as the asymmetric load.
* Create a condition that adds Q to the magnitude of the external loads.
* Use a number slider in Grasshopper to change the anchor point of the asymmetric load.
{% endhint %}

### Task 4 - Constrain the force diagram

Constrain the design space to those funiculars in compression whose horizontal thrust is equal to 100 kN.

{% hint style="info" %}
Use the solution from Tasks 2 as a base to solve this task.
{% endhint %}

### Task 5 - Dimensioning

The algorithm from the tutorial displays pipes that show the magnitude of the internal force within the elements. Change this so that the pipes display the required diameter of material. To do this, dimension first the required cross-sectional area using the formula below and after calculate the diameter. For the elements in compression, use steel profiles with a characteristic strength of 235 N/mm2 and, for the elements in tension, use steel cables with a characteristic strength of 1670 N/mm2. Use the safety factor (1.05) to obtain the design strength.

$$
Areq = Nd/fd
$$

{% hint style="info" %}
* Areq stands for required area.
* Nd stands for design internal force (your internal forces are already "design" forces)
* fd stands for design yield strength. You got the characteristic yield strength. In order to obtain the design yield strength divide this by the safety factor (1.05).
{% endhint %}

### Task 6 - Compact algorithm

The algorithm from the tutorial is built up in sections. Put it now all together in a single Python component.

{% hint style="danger" %}
When you put together the pieces of code, it will give you the error "index out of range". To solve this issue, delete the last line of action (Ll\_LOA\[-1]) before creating the internal forces. This is because in the algorithm, in order to create the resultant, we have added a duplicate of the last line of action. This error does not appear when we build the algorithm in separated parts because when in point 3. Internal forces we again need to use the lines of action of the loads to build the form diagram, we are inputting the original unaltered list of LOA, rather than that one that contains a duplicate.
{% endhint %}

{% hint style="info" %}
Use the solution from Tasks 5 as a base to solve this task.
{% endhint %}

### Task 7 - Golden Gate bridge

Using the algorithm from Task 6 as a base, create the structure below.

{% embed url="https://vimeo.com/769584393" %}

{% hint style="success" %}
Hints:

* Use three times the compact algorithm from Task 6 to build the three sections of the bridge.
* Start with the section on the right. Then, create the central section and finally the section in the left.
* Chain the force diagrams using the last point of the loadline of one force diagram as the first point for the next one.
* In addition to the three Python components (one per section), you will have to create a forth component
{% endhint %}
