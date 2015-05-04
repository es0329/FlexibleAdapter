# FlexibleAdapter

The functionalities are taken from different blogs (see at the bottom of the page), merged and methods have been improved for speed and scalability, for all activities that use a RecycleView.

* At lower class there is SelectableAdapter that provides selection functionalities and it's able to _maintain the state_ after the rotation, you just need to call the onSave/onRestore methods from the activity.
* Then, the class FlexibleAdapter handles the content paying attention at the animations (calling notify only for the position. _Note:_ you still need to set your animation to the RecyclerView when you create it in the activity).
* Then you need to extend over again this class. Here you add and implements methods as you wish for your own ViewHolder and your Domain/Model class (data holder).

I've put the click listeners inside the ViewHolder and the set should be done at the creation and not in the Binding method, that is called at each invalidate when calling notify..() methods.

Also note that this adapter handles the basic clicks: _single_ and _long clicks_. If you need a double tap you need to implement the android.view.GestureDetector.


**Notes:**
There's an example adapter which does not compile because you need to change the classes with the ones you have in your project.


I still have to improve it, so keep an eye on it.
I would like to add some new functionalities, like the Undo.



***

I've used these blogs as starting point:

http://enoent.fr/blog/2015/01/18/recyclerview-basics/

https://www.grokkingandroid.com/statelistdrawables-for-recyclerview-selection/