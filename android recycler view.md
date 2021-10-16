Android Recycler View


Recycler View Animation - https://www.youtube.com/watch?v=uh6lKnfp5hY&ab_channel=BrandanJones
Recycler View Complete Explanation - https://www.youtube.com/watch?v=9rcrYFO1ogc&ab_channel=yoursTRULY
Sample Project with different variants of Recycler view - https://github.com/trulymittal/RecyclerView


Components of Recycler View

Recycler View - Parent Container - XML
Row Item - each item in recycler view - XML
Collection - collection of data which is shown in recycler view
Adapter - Manages collection and viewholder(s) It passes data from collection to viewholder
View Holder - Takes Each collection item and uses it to populate each row item
Steps for setting up basic recycler view

Create recycler view ViewGroup in XML and refer to it using findViewById in corresponding Activity. (inside oncreate)
Create Recycler Adapter class
Create ViewHolder class inside Adapter class. It extends from recyclerview.viewHolder . implement the constructor .
Adapter class extends RecyclerView.Adapter<>() Pass the type as ViewHolder created above. eg. RecyclerAdapter.ViewHolder
Implement methods for RecyclerAdapter
getItemCount() -> Returns collection size
onCreateViewHolder() -> This method creates rows and returns viewHolder. Note that it is only called a few more times than the number of items shown on screen at once.
Create RowXml if not done yet.
Create Instance of Layout Inflater .from(parent.context)
Create view by layoutInflater.inflate(R.layout.row_item, parent, false)
Create viewHolder by passing view created above as argument
return viewholder
viewType argument of this method is used if we want to return multiple view holders
onBindViewHolder() - implement after writing viewholder class logic
Write logic in viewHolder class -> ViewHolder class has access to all individual views (like image view, textview etc) inside each rowitem.
The viewholder class constructor takes itemView parameter (of type view). This itemView is now our row xml. Hence we can use itemView.findViewById to refer to all elements in each row.
Now inside the Activity where we had declared RecyclerView, we should declare Recycler Adpater
Attach Layout Manager to RecyclerView to Specify which type of recycler view we are using.
eg. recyclerView.setLayoutManager(LinearLayoutManager(this))
Alternatively we can open xml of recyclerView and use property app:layoutManager="androidx.recyclerview.widget.LinearLayoutManager"
Attach RecyclerAdpater to recycler View. eg. recyclerview.setAdapter(recyclerAdapter)
Now lets implement onBindViewHolder() -> This takes holder and position as arguments and used to set data in each row. Hence it is called for each item in collection as opposed to onCreateViewHolder()
holder is obj of type ViewHolder. Hence the image view/textview elements we had referred to inside ViewHolder Constructor are available here.
We can use position to set values. eg. holder.rowTextView.setText(position.toString())

Summary to setup Up basic Recycler View.

Recycler View XML -> Activity -> Attach Layout Manager to xml OR activity. -> Row xml
Create Recycler Adapter -> inner ViewHolder -> viewholder extends -> implement viewholder constructor -> extend recyclerAdapter and pass in viewholder as type -> implement recycleradpater methods
Return size in getItemCount() -> Create layoutInflater from parent.context, view by row xml; parent; false and viewholder from view. Return viewholder from onCreateViewHolder()
Refer to row elements in viewHolder constructor using itemview -> Use this holder to set values to elements in onBindViewHolder()
Create instance of recyclerAdapter in Activity. Attach RecylerAdapter to recycler view.


Passing Collection to RecyclerView


Create Collection in Activity. Add data to it and pass to RecyclerAdapter while creating its instance.
Create a property for the collection and constructor to populate from this collection in Adapter class
Make changes to Adapter Methods
getItemCount() -> return collection.size
onBindViewHolder() -> now you can access collection items using position and use it to set current row.

Setting up Divider


Create instance of DividerItemDecoration in Activity. It takes context and orientation (of recycler View)
Attach to recyclerView using recyclerView.setItemDecoration(dividerItemDecoration)


Adding OnClick Listener to Items


Attach onClickListener to itemview inside viewHolder constructor. It takes context as parameter
Implement View.OnClickListener interface for ViewHolder
Override OnClick method in viewHolder. It has access to view argument. We can use it to get context. eg, view.getContext(). Also current position is provided by getAdapterPosition()
For longClickListener -> Attach onLongClickListener inside view holder constructor (similar to onClickListener)
Either override OnLongClickListener like onClick OR
We can pass onLongClickListener while attaching to itemview itself. Return true to mention that long click was handled
If making changes to collection, then trigger appropriate methods like notifyItemRemoved() etc. It takes position as argument

Ripple effect to Items

Add following change to row xml parent view group -> add property : "?attr/selectableItemBackground" to android:background (or foreground)
