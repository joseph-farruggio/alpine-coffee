```html
<!-- Option 1 -->
<div x-data="{open: false}">
    <button @click="open = !open">Toggle Menu</button>

    <div x-show="open" x-transition>
        <a href="#">Menu Item 1</a>    
        <a href="#">Menu Item 2</a>    
        <a href="#">Menu Item 3</a>    
    </div>
</div>
```

```html
<!-- Option 2 -->
<div x-data="{open: false}">
    <button @click="open = !open">Toggle Menu</button>

    <div 
        x-show="open"
        x-transition:enter="transition ease-out duration-100"
        x-transition:enter-start="transform opacity-0 scale-95"
        x-transition:enter-end="transform opacity-100 scale-100"
        x-transition:leave="transition ease-in duration-75"
        x-transition:leave-start="transform opacity-100 scale-100"
        x-transition:leave-end="transform opacity-0 scale-95">
        <a href="#">Menu Item 1</a>    
        <a href="#">Menu Item 2</a>    
        <a href="#">Menu Item 3</a>    
    </div>
</div>
```