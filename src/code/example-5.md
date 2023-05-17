```html
<div x-data="notify()" @notify.window="add($event)">
    <!-- Notification -->
    <template x-for="notification in notifications" :key="notification.id">
        <div x-data="notification()" x-show="show" x-transition.duration.500ms>
            <div class="flex items-start">
                <!-- Icons -->
                <div x-show="notification.type === 'info'">
                    <!-- Info icon -->
                </div>

                <div x-show="notification.type === 'success'">
                    <!-- Success icon -->
                </div>

                <div x-show="notification.type === 'error'">
                    <!-- Error icon -->
                </div>

                <!-- Notification Content -->
                <p x-text="notification.content"></p>

                <!-- Remove button -->
                <button @click="transitionOut()" type="button">
                    Dispatch Notification
                </button>
            </div>
        </div>
    </template>
</div>

<!-- Examples of how to dispatch the `notify` event with variable text and type -->
<form
    x-data="{content: 'Something happened!', type: 'info'}"
    class="max-w-sm w-full"
    x-on:submit.prevent="$dispatch('notify', { content, type })">
    
    <!-- The message -->
    <input id="message" x-model="content" type="text">

    <!-- The type -->
    <select id="type" x-model="type" type="text">
        <option value="info">Info</option>
        <option value="success">Success</option>
        <option value="error">Error</option>
    </select>
    
    <!-- Submit form and dispatch event -->
    <button>Dispatch notification</button>
</form>

<script>
    document.addEventListener('alpine:init', () => {
        Alpine.data('notify', () => ({
            show: false,
            init() {
                this.$nextTick(() => this.show = true)

                setTimeout(() => this.transitionOut(), 2000)
            },
            transitionOut() {
                this.show = false

                setTimeout(() => this.remove(this.notification), 500)
            }
        }))

        Alpine.data('notification', () => ({
            show: false,
            init() {
                this.$nextTick(() => this.show = true)

                setTimeout(() => this.transitionOut(), 2000)
            },
            transitionOut() {
                this.show = false

                setTimeout(() => this.remove(this.notification), 500)
            },
        }))

       
    })
</script>
```