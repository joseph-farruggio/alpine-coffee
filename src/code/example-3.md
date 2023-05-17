```html
<!-- Option 1 -->
<div x-data="{color: red}">
    <button @click="color = 'red'">Red</button>
    <button @click="color = 'green'">Green</button>

    <div :class="color == 'red' ? 'bg-red-700' || 'bg-green-700'">
        <p>The current color is <span x-text="color"></span></p>
    </div>
</div>
```