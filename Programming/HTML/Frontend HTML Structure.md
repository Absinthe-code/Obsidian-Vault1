#FAT-Stack #Firebase #AlpineJS #Tailwind

## Tailwind

Formatting rules:

| 1.Positioning  | 2.Display      | 3.Background | 4.Text   | 5.Visibility |
| -------------- | -------------- | ------------ | -------- | ------------ |
| fixed/absolute | flex/grid      | color        | position | hidden       |
| top/bottom     | items position | hover        | font     |              |
| width          | justification  |              | size     |              |
| height         | gap            |              | color    |              |
| padding        |                |              |          |              |
| margin         |                |              |          |              |
| border         |                |              |          |              |

## Head

``` html
<script
      defer
      src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"
></script>
<script src="https://cdn.tailwindcss.com"></script>
```
## Header

```html
<header
      class="fixed top-0 w-full h-16 px-4 flex justify-between items-center bg- zinc-800 font-semibold text-sm md:text-base text-gray-300"
    >
      <nav class="h-full flex items-center">
        <ul class="h-full flex items-center">
          <li class="">
            <a
              href=""
              class="px-4 py-2 rounded-lg flex items-center hover:bg-zinc-700"
              >Left Text 1</a
            >
          </li>
          <li class="hidden md:block">
            <a
              href=""
              class="px-4 py-2 rounded-lg flex items-center hover:bg-zinc-700"
              >Left Text 1</a
            >
          </li>
        </ul>
      </nav>
      <nav class="h-full flex items-center">
        <ul class="h-full flex items-center">
          <li class="md:hidden">
            <a
              href=""
              class="px-4 py-2 rounded-lg flex items-center hover:bg-zinc-700"
            >
              Center Text</a
            >
          </li>
        </ul>
      </nav>
      <nav class="h-full flex items-center">
        <ul class="h-full flex items-center">
          <li class="hidden md:block">
            <a
              href=""
              class="px-4 py-2 rounded-lg flex items-center hover:bg-zinc-700"
              >Right Text 1</a
            >
          </li>
          <li class="hidden md:block">
            <a
              href=""
              class="px-4 py-2 rounded-lg flex items-center hover:bg-zinc-700"
              >Right Text 2</a
            >
          </li>
          <li class="hidden md:block">
            <a
              href=""
              class="px-4 py-2 rounded-lg flex items-center hover:bg-zinc-700"
              >Right Text 3</a
            >
          </li>
          <li class="md:hidden" x-data="{active: false}">
            <a
              class="px-4 py-2 rounded-lg flex items-center hover:bg-zinc-700"
              x-on:click="active = !active"
              x-bind:class="active ? 'bg-zinc-700' : 'bg-zinc-800'"
              >Menu</a
            >
            <div
              class="absolute inset-0 w-screen h-screen bg-black opacity-40"
              x-on:click="active = !active"
              x-bind:class="active ? 'block' : 'hidden'"
            ></div>
            <ul
              class="absolute py-2 mt-6 mx-2 min-w-48 right-0 flex-col rounded-xl bg-zinc-800"
              x-bind:class="active ? 'block' : 'hidden'"
            >
              <li class="">
                <a
                  href=""
                  class="px-4 py-2 rounded-lg flex items-center hover:bg-zinc-700"
                  >Right Text 1</a
                >
              </li>
              <li class="">
                <a
                  href=""
                  class="px-4 py-2 rounded-lg flex items-center hover:bg-zinc-700"
                  >Right Text 2</a
                >
              </li>
              <li class="">
                <a
                  href=""
                  class="px-4 py-2 rounded-lg flex items-center hover:bg-zinc-700"
                  >Right Text 3</a
                >
              </li>
            </ul>
          </li>
        </ul>
      </nav>
    </header>
```

remember to eliminate the href when clicking
clicking anywhere goes back

### Functioning Menu

```html
<li class="md:hidden">
	<a
		class="h-12 p-4 rounded-lg flex items-center hover:bg-zinc-700"
		x-data="{active: false}"
		x-on:click="active = !active"
		x-bind:class="active ? 'bg-zinc-700' : 'bg-zinc-800'"
		>Menu(md:hidden)</a
	>
</li>
```