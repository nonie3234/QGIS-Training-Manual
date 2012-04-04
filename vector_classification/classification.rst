|LS| Classification
===============================================================================

Labels are a good way to communicate information such as the names of
individual places, but they can't be used for everything. For example, let's
say that someone wants to know which the farms are in. Using labels, you'd get
this:

.. image:: ../_static/classification/001.png

Obviously this is not ideal, so we need another solution. That's what this
lesson is about!

**The goal for this lesson:** To learn how to classify vector data effectively.

|basic| |FA| Classifying nominal data
-------------------------------------------------------------------------------

Open :guilabel:`Layer Properties` and go to the :guilabel:`Style` tab. Click on
the dropdown that says :guilabel:`Single Symbol`:

.. image:: ../_static/classification/002.png

Change it to :guilabel:`Categorized` and the interface will change:

.. image:: ../_static/classification/003.png

Change the :guilabel:`Column` to :guilabel:`TOWN` and the :guilabel:`Color
ramp` to :guilabel:`random`:

.. image:: ../_static/classification/004.png

Click the button labeled :guilabel:`Classify` and then click :guilabel:`OK`.
You'll see something like this:

.. image:: ../_static/classification/005.png

If you click the arrow (or plus sign) next to :guilabel:`rural` in the
:guilabel:`Layer list`, you'll see the categories explained:

.. image:: ../_static/classification/006.png

So, this is useful! But it hurts your eyes to look at it, so let's see what we
can do about that.

Open :guilabel:`Layer Properties` and go to the :guilabel:`Style` tab again.

Let's change the symbol:

.. image:: ../_static/classification/007.png

Get rid of the outline the same way you did before, and click :guilabel:`OK`.
(If you need to, go back to the lesson where we covered this to remember how
it's done.)

Once you're back in the :guilabel:`Style` dialog, click the :guilabel:`Delete
all` button:

.. image:: ../_static/classification/008.png

This gets rid of the ugly classes so you can try again. Click
:guilabel:`Classify` again, and the new symbols will appear. You'll notice they
don't have outlines, because you just removed the outlines!

Now change the color for each town by double-clicking on the colored block
representing its symbol:

.. image:: ../_static/classification/009.png

Use your own colors, but make sure they're not too bright, so that the
resulting map isn't as ugly as the old one. In the example, we'll use these
colors:

.. image:: ../_static/classification/011.png

This gives us a nice map:

.. image:: ../_static/classification/010.png

(Only :guilabel:`rural` and :guilabel:`water` are switched on here.)

By the way, there's one category that's empty:

.. image:: ../_static/classification/012.png

You can delete it by selecting it and then clicking the :guilabel:`Delete`
button. This only gets rid of the symbol, not the data, so don't worry about
messing up; you're not actually deleting anything that you can't recover.

Remember to save your map now so that you don't lose all your hard-earned
changes!

|basic| |TY| More classification
-------------------------------------------------------------------------------

If you're only following the basic-level content, use the knowledge you gained
above to classify the towns. Use darker colors to set the towns apart from the
farms.

|moderate| |FA| Ratio classification
-------------------------------------------------------------------------------

There are four types of classification: *nominal*, *ordinal*, *interval* and
*ratio*.

In nominal classification, the categories that objects are classified into are
name-based; they have no order. For example: town names, district codes, etc.

In ordinal classification, the categories are arranged in a certain order. For
example, world cities are given a rank depending on their importance for world
trade, travel, culture, etc.

In interval classification, the numbers are on a scale with positive, negative
and zero values. For example: height above/below sea level, temperature
above/below freezing (0 degrees Celsius), etc.

In ratio classification, the numbers are on a scale with only positive and zero
values. For example: temparature above absolute zero (0 degrees Kelvin),
distance from a point, the average amount of traffic on a given street per
month, etc.

In the example above, we used nominal classification to assign each farm to the
town that it is administered by. Now we will use ratio classification to
classify the farms by area.

First, save your rural symbology (if you want to keep it) by clicking on the
:guilabel:`Save Style ...` button in the :guilabel:`Style` dialog. We're going
to reclassify the layer, so existing classes will be lost if not saved.

Once you're done, close the :guilabel:`Style` dialog and open the layer
attributes for the :guilabel:`rural` layer. We want to classify these farms by
area, but there's a problem: they don't have an area field! We'll have to make
one.

First, enter edit mode by clicking this button:

.. image:: ../_static/classification/013.png

Then add a new column with this button:

.. image:: ../_static/classification/014.png

A dialog appears. Set it up like this:

.. image:: ../_static/classification/015.png

Now click :guilabel:`OK`. The new field will be added (at the far right of the
table; you may need to scroll horizontally to see it). However, at the moment
it is not populated, it just has a lot of :kbd:`NULL` values.

To solve this problem, we'll need to calculate the areas. Open the field
calculator:

.. image:: ../_static/classification/016.png

You'll get this dialog:

.. image:: ../_static/classification/018.png

Change the values at the top of the dialog to look like this:

.. image:: ../_static/classification/017.png

In the :guilabel:`Function List`, select :menuselection:`Geometry --> $area`:

.. image:: ../_static/classification/019.png

Double-click on it so that it appears in the :guilabel:`Expression` field, then
click :guilabel:`OK`. Now your :kbd:`AREA` field is populated with values!
Admire them, then close the attribute table.

Open the :guilabel:`Layer properties` dialog's :guilabel:`Style` tab again,
then change the classification style from :guilabel:`Classified` to
:guilabel:`Graduated`:

.. image:: ../_static/classification/020.png

Change the :guilabel:`Column` to :guilabel:`AREA`:

.. image:: ../_static/classification/021.png

Under :guilabel:`Color ramp`, choose the option :guilabel:`New color ramp...`
to get this dialog:

.. image:: ../_static/classification/022.png

Choose :guilabel:`Gradient` (if it's not selected already) and click
:guilabel:`OK`. You'll see this:

.. image:: ../_static/classification/023.png

You'll be using this to denote area, with small areas as :guilabel:`Color 1`
and large areas as :guilabel:`Color 2`, so choose colors accordingly. In the
example, the result looks like this:

.. image:: ../_static/classification/024.png

Click :guilabel:`OK` and choose a suitable name for the new color ramp. Click
:guilabel:`OK` after filling in the name. Now you'll have something like this:

.. image:: ../_static/classification/025.png

Leave everything as-is and click :guilabel:`Apply`:

.. image:: ../_static/classification/026.png


.. _backlink-classification-refine-1:

|moderate| |TY| Refine the classification
-------------------------------------------------------------------------------

Using your existing knowledge, get rid of the lines between the classes. Then
change the values of :guilabel:`Mode` and :guilabel:`Classes` until you get a
classification that makes sense.

:ref:`Check your results <classification-refine-1>`

|hard| |FA| Rule-based classification
-------------------------------------------------------------------------------

It's often useful to combine multiple criteria for a classification, but
unfortunately normal classification only takes one attribute into account.
That's where rule-based classification comes in handy. Switch the
classification style to :guilabel:`Rule-based`. You'll get this:

.. image:: ../_static/classification/029.png

Click the :guilabel:`Add` button. In the dialog that appears, click the
ellipsis :guilabel:`...` button next to the :guilabel:`Filter` text area. Using
the query builder that appears, enter the criterion :kbd:`AREA >= 0.00085` and
choose a dark color for it. Then add the criterion :kbd:`AREA <= 0.00085` and
choose a light color. Finally, add the criterion :kbd:`TOWN != 'Swellendam
Rural'` and assign it the color black, with transparency at :kbd:`85%`.

Click on the :kbd:`TOWN ...` criterion in the list of rules, and then on
:guilabel:`Increase priority`. Your dialog should look like this:

.. image:: ../_static/classification/030.png

Apply this symbology, and your map will look like this:

.. image:: ../_static/classification/031.png

Now you have two area classes, with the farms in the Swellendam Rural area
emphasized.

|IC|
-------------------------------------------------------------------------------

Symbology allows us to represent the attributes of a layer in an easy-to-read
way. It allows us as well as the map reader to understand the significance of
features, using any relevat attributes that we choose. Depending on the
problems you face, you'll apply different classification techniques to solve
them.

|FR|
-------------------------------------------------------------------------------

|WN|
-------------------------------------------------------------------------------

Now we have a nice-looking map, but how are we going to get it out of QGIS and
into a format we can print out, or make into an image or PDF? That's the topic
of the next lesson!