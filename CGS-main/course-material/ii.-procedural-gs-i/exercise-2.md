---
description: Single node bridge in Grasshopper
---

# Exercise B-1

{% hint style="warning" %}
Complete the exercises below and submit the files **by 9:45 am on Friday, October 11th.**

File 1: Rhinoceros file

File 2: Grasshopper file (only one file for all tasks!)

File 3: PDF of the word document file with answers

Please follow the file naming convention as shown in the [**Syllabus**](../../syllabus.md#submissions).

[**Submit here**](https://moodle-app2.let.ethz.ch/course/view.php?id=23670\&lang=en)
{% endhint %}

{% hint style="info" %}
Use the Rhinoceros file from the tutorial as a base to solve the tasks. We recommend that you solve the tasks in a Grasshopper file different than that of the tutorial. Then, answer the questions in the docx file. You will find all these files [**here**](./#files).
{% endhint %}

### Task 0 - Flow chart

Draw a simple flowchart of the algorithm from Tutorial 1.&#x20;

A flowchart is a step-by-step approach until you find the answer. Flowcharts help you to visualize the processes in small steps and they are very similar to how the computer executes your instructions.

![](https://files.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-M730QpQnbAMvz44bqhc%2F-MNht34RYVKlCmOCcR92%2F-MNiECpXmHCeJT14YSZs%2Fimage.png?alt=media\&token=13c41acb-ddda-47f9-a01e-89861de8fc7c)

|   Function   |        Shape       |                                   Explanation                                   |
| :----------: | :----------------: | :-----------------------------------------------------------------------------: |
|   Start/End  | rounded rectangles | Start is required of all flowcharts, while some flowcharts may not have an end. |
|    Process   |      rectangle     |               It involves the action, to do something. e.g. add 1               |
| Input/Output |    parallelogram   |      It indicates that manual operation is needed. e.g. type in the number      |
|   Decision   |       rhombus      |                        e.g. Is the number bigger than 10?                       |
|     Arrow    |        arrow       |                       It indicates the flow of the chart.                       |

#### Example:

In this algorithm, we want to calculate the material cost of a gridshell made from bar elements. The bar elements that have a length larger than 3 meters have a different cost than those shorter than 3 meters. The algorithm picks a bar, checks its length and stores the data in the corresponding list (small or large). It does the same for all the rest of bars. As a result we know how many short and long elements there are and therefore we can calculate the cost.

![](https://github.com/BlockResearchGroup/CSD2\_2022/blob/5319ae679b8e41fbf62b45afee4b4c2794c35233/2\_Geometry/Tutorial2/img/week1\_ex1.png?raw=true)

### Task 1 - Control of force diagram for single-node bridge

In the tutorial, we saw how to create an interactive graphic statics model of a single-node bridge spanning over a canyon with interactive control of the **form diagram.** Now, in this exercise, the task is to modify the definition to allow for the **interactive control** of the **force diagram.**

Implement the interactive **force** control in your Grasshopper definition!

{% hint style="info" %}
This means that instead of defining the lines of action as directions through the form diagram, the lines of actions are determined through the modification of the force diagram which thus dictates the form diagram: the point can be dragged in the force diagram and thus the form diagram adapts accordingly (see video below).
{% endhint %}

![](../../.gitbook/assets/aim\_exercise\_1\_fast4.gif)

### Task 2 - Limitation of force magnitudes

A geotechnical engineer examined the cliffs of the canyon and thus dictates that they can support a **maximum force of 12kN**.

_Implement the limit of the support forces **graphically** in your force diagram with a **warning** symbol in your Grasshopper definition!_

{% hint style="danger" %}
**The solution must be graphical.** Mathematical checks with the `<` component checking if the value of the force magnitude is below the threshold will not be graded!
{% endhint %}

### Task 3 - Single-sided bridge

The construction company states that the left cliff is much more accessible than the right cliff and therefore design options are to be explored, where **both** the left and the right elements connect **only to the left cliff**.‌

_Implement this **single-sided** bridge in your Grasshopper definition!_

{% hint style="info" %}
Think of the two mixed-tension-and-compression basic nodal configurations and how these could be rotated.
{% endhint %}

### Task 4 - Check for fractured rocks

Further, the geotechnical engineer identified **regions** of **fractured rocks**, where it is not possible to anchor the cables.

_Implement a **warning display** if the anchors are in the fractured region in your Grasshopper definition!_

![](../../.gitbook/assets/aim\_exercise\_2\_fast4.gif)

### Task 5 - Favourite designs

Find two existing bridge structures that can be simplified to a single-node structure as references. Then, design your favourite bridge configurations. These designs must respect both **form and force constraints** of the limited force magnitudes of 12kN from Task 2 and the fractured rocks from Task 4. They can be either single-sided or both-sided.

## Useful components

To verify if a point is contained in one or multiple closed curves, the `Point in Curves` component is useful. If the point is outside, coincident (on the boundary), or inside the curve, the relationship output will be 0, 1, or 2, respectively. If the containment of multiple curves should be tested, the list of curves must be grafted, so that the point is tested for each curve. The output must then be flattened again. You might also need the `Mass Addition` component.

![](<../../.gitbook/assets/image (67).png>)

To display a warning at a certain condition/location, the `Symbol Display` component is useful. As input, it requires a location as a point and display settings from the `Symbol (Simple)` component. To modify the symbol style, size or colour, right-click on the input parameters of the component.

![](<../../.gitbook/assets/image (136).png>)

Further, the `Curve | Curve` component will be useful to find the intersection of two curves. Almost all other components required to solve the tasks should be familiar from the tutorials.
