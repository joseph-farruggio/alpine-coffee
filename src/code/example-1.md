```html
<div x-data="{name: null, coffee: null}">
    
    <label for="name">Your name</label>
    <input type="text" id="name" x-model="name" placeholder="Enter your name">

    <label>Your favorite coffee</label>
    <select x-model="coffee">
        <option value="Select Coffee" hidden>Select Coffee</option>
        <option value="Americano">Americano</option>
        ...
    </select>

    <p>
        Hey! My name is <span x-text="name || '${name}'"></span>
        and my favorite coffee to drink is the 
        <span x-text="coffee || '${coffee}'"></span>.
    </p>
</div>
```