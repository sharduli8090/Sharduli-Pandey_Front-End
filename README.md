<h1>Sharduli Pandey Submission Frontend</h1>

<h3>
1- Explain what the simple List component does.
</h3>
<div>
The List component renders a list of items passed as props. It manages the selected index state using the useState hook and resets the selected index when the items array changes using the useEffect hook. Each item is rendered as a SingleListItem component which is a memoized component to improve performance. The SingleListItem component displays the text and changes the background color based on whether the item is selected or not. It also triggers a callback function when clicked which updates the selected index in the List component's state. The List component uses PropTypes to validate the items prop as an array of objects with a text property of type string.
</div>

<h3>
2- What problems / warnings are there with code?
</h3>
<div>
1- In the WrappedSingleListItem component, the onClick handler should be a function that calls onClickHandler with the index parameter and should be called by arrow function.
2- In the WrappedListComponent component, the selectedIndex should be written first and setSelectedIndex second and the state variable setSelectedIndex is not correctly initialized. It should be initialized to useState(null), which returns an array with the state variable and the function to update it.  
3- In the WrappedListComponent component, the items prop is not correctly defined in the propTypes. The array propType should be defined using PropTypes.arrayOf(), and the shape object should be defined using PropTypes.shape(). 
4- In the WrappedListComponent component, the isSelected prop passed to the SingleListItem component is always truthy, even when it should be falsy. This is because the selectedIndex state is initialized to null, which is truthy. To fix this, change the isSelected prop to be a boolean value that compares selectedIndex with the current index.
5- The items prop passed to the WrappedListComponent component is null. In that case, the useEffect hook is called with null as the dependency, and it tries to set the setSelectedIndex state to null, which causes the error.
</div>
<h3>The Optimized code is in the WrappedSingleListItem Component.</h3>