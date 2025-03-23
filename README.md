# observerDemo

<div class="container">
  <h2>Output Verified</h2>
  <pre>
    First state change: 15
    Hex String: F
    Octal String: 17
    Binary String: 1111

    Second state change: 10
    Hex String: A
    Octal String: 12
    Binary String: 1010
  </pre>
    </div>

  <h1>Observer Pattern Explanation</h1>
    
  <h2>What is the Observer Pattern?</h2>
  <p>The Observer Pattern is a behavioral design pattern where an object (Subject) maintains a list of dependents (Observers) and notifies them of any state changes.</p>
    
  <h2>Key Components</h2>
    <ul>
        <li><strong>Subject:</strong> Maintains a list of observers and notifies them of state changes.</li>
        <li><strong>Observer:</strong> Defines an interface for objects that should be notified of changes.</li>
        <li><strong>Concrete Observers:</strong> Implement the Observer interface and update themselves based on Subject's state.</li>
    </ul>

  <h2>EventManager Class</h2>
    <p>The <code>EventManager</code> class is responsible for handling subscriptions, unsubscriptions, and notifying observers when an event occurs.</p>
    <ul>
        <li>Uses a <code>HashMap</code> to store event types and their listeners.</li>
        <li><code>subscribe</code>: Adds a listener to an event.</li>
        <li><code>unsubscribe</code>: Removes a listener from an event.</li>
        <li><code>notify</code>: Calls the <code>update</code> method of each listener when an event occurs.</li>
    </ul>

  <h2>Editor Class</h2>
    <p>The <code>Editor</code> class acts as the subject that generates events. It has an <code>EventManager</code> instance to manage listeners.</p>
    <ul>
        <li><code>openFile</code>: Notifies listeners about the file opening event.</li>
        <li><code>saveFile</code>: Notifies listeners about the file-saving event.</li>
    </ul>

  <h2>Notification Classes</h2>
    <h3>EmailNotificationListener</h3>
    <p>Sends an email when a specific event (open/save) occurs.</p>
    <ul>
        <li>Implements <code>EventListener</code> interface.</li>
        <li><code>update</code> method prints an email notification message.</li>
    </ul>

  <h3>LogOpenListener</h3>
    <p>Writes an event message to a log file when a file is opened.</p>
    <ul>
        <li>Implements <code>EventListener</code> interface.</li>
        <li><code>update</code> method prints a log message.</li>
    </ul>
    
  <h2>Observer Classes</h2>
    <p>The observer classes listen to the state changes in the subject.</p>
    <ul>
        <li><strong>BinaryObserver:</strong> Converts the state to binary and prints it.</li>
        <li><strong>OctalObserver:</strong> Converts the state to octal and prints it.</li>
        <li><strong>HexaObserver:</strong> Converts the state to hexadecimal and prints it.</li>
    </ul>

  h2>Execution Flow</h2>
    <p>When the state of the subject changes, it notifies all observers, triggering their respective update methods.</p>
    
  <h2>Demo Class</h2>
    <p>The <code>Demo</code> class initializes the system, registers observers, and triggers events to demonstrate how the pattern works.</p>
