# Tutorial Walkthrough by CodeBucks via YouTube

This is a walkthrough tutorial via the YouTube channel CodeBucks. 
    *Link to Video: https://youtu.be/Q92WWJt2wsk

# Notes.txt File Content:

Every React component goes through these three phases:
    - Mounting: When React mounts or sends the component to the DOM.
    - Updating: When React updated it's component whenever there is a change of the state or props.
    - Unmounting: When React removes the component from the DOM tree.

^ Shows further example by referencing the diagram at this link that also links to React Lifecycle docs:
    https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/

Mounting Phase: 

    - Constructor()
        constructor(props) {
            super(props)
        }
            ~ the first method which invokes in the Mounting Phase

    - render()
            ~ As the name suggests it is the method that actually outputs or renders HTML to the DOM.
            ~ The render() method is the only required method in a class component.
            ~ It should always be paired with the return keyword.
            ~ A render() method has to be pure with no side-effects. 
            ~ You cannot modify the component state(setState) within the render().

    - componentDidMount()
            ~ This method is called after your component is mounted and ready.
            ~ In this method you can initiate API calls, if you need to load data from a remote endpoint, and also use setState() method.
            ~ Calling the setState() in componentDidMount() will update state and cause another rendering, but it will happen before the browser updates the UI.

Updating Phase:

    - componentDidUpdate()
            ~ componentDidUpdate() is invoked immediately after updating occurs.
            ~ This method is not called for the initial render.
            ~ You can call setState() immediately in componentDidUpdate() but note that unlike with componentDidMount(), to use setState in this method it must be wrapped in a condition.
            ~ componentDidUpdate() will not be invoked if shouldComponentUpdate() returns false.

Unmounting Phase:

    - componentWillUnmount()
            ~ This lifecycle method is called just before the component is unmounted and destroyed.
            ~ This method is used to perform any necessary cleanup such as invalidating timers, canceling network requests, or cleaning up any subscriptions that were created in componentDidMount().
            ~ You should not call setState() in componentWillUnmount() because the component will never be re-rendered.
