```html
<div x-data="{
    people: [
        {
            name: 'John Harrison', 
            avatar: 'https://i.pravatar.cc/150?img=52', 
            job: 'CTO of ACME'}, 
        {
            name: 'Alex White', 
            avatar: 'https://i.pravatar.cc/150?img=12', 
            job: 'Marketing Intern'
        }, 
        {
            name: 'Sara West', 
            avatar: 'https://i.pravatar.cc/150?img=49', 
            job: 'Operations Manager'}]
        }
    ]">
    
    <template x-for="person in people" :key="person.name">
        <div>
            <img :src="person.avatar">
            <div>
                <p x-text="person.name"></p>
                <p x-text="person.job"></p>
            </div>
        </div>
    </template>
</div>
```