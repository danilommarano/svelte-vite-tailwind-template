<script lang="ts">
  import type { SvelteComponent } from 'svelte';

  export let icon: SvelteComponent | any;
  export let color: string;

  // Define the tailwind color classes based on the provided colors
  type ColorClasses = {
    [color: string]: string;
  };
  let colorClasses: ColorClasses = {
    slate: 'bg-slate-100 text-slate-500 group-hover:from-slate-100 group-hover:to-slate-200',
    gray: 'bg-gray-100 text-gray-500 group-hover:from-gray-100 group-hover:to-gray-200',
    zinc: 'bg-zinc-100 text-zinc-500 group-hover:from-zinc-100 group-hover:to-zinc-200',
    neutral: 'bg-neutral-100 text-neutral-500 group-hover:from-neutral-100 group-hover:to-neutral-200',
    stone: 'bg-stone-100 text-stone-500 group-hover:from-stone-100 group-hover:to-stone-200',
    red: 'bg-red-100 text-red-500 group-hover:from-red-100 group-hover:to-red-200',
    orange: 'bg-orange-100 text-orange-500 group-hover:from-orange-100 group-hover:to-orange-200',
    amber: 'bg-amber-100 text-amber-500 group-hover:from-amber-100 group-hover:to-amber-200',
    yellow: 'bg-yellow-100 text-yellow-500 group-hover:from-yellow-100 group-hover:to-yellow-200',
    lime: 'bg-lime-100 text-lime-500 group-hover:from-lime-100 group-hover:to-lime-200',
    green: 'bg-green-100 text-green-500 group-hover:from-green-100 group-hover:to-green-200',
    emerald: 'bg-emerald-100 text-emerald-500 group-hover:from-emerald-100 group-hover:to-emerald-200',
    teal: 'bg-teal-100 text-teal-500 group-hover:from-teal-100 group-hover:to-teal-200',
    cyan: 'bg-cyan-100 text-cyan-500 group-hover:from-cyan-100 group-hover:to-cyan-200',
    sky: 'bg-sky-100 text-sky-500 group-hover:from-sky-100 group-hover:to-sky-200',
    blue: 'bg-blue-100 text-blue-500 group-hover:from-blue-100 group-hover:to-blue-200',
    indigo: 'bg-indigo-100 text-indigo-500 group-hover:from-indigo-100 group-hover:to-indigo-200',
    violet: 'bg-violet-100 text-violet-500 group-hover:from-violet-100 group-hover:to-violet-200',
    purple: 'bg-purple-100 text-purple-500 group-hover:from-purple-100 group-hover:to-purple-200',
    fuchsia: 'bg-fuchsia-100 text-fuchsia-500 group-hover:from-fuchsia-100 group-hover:to-fuchsia-200',
    pink: 'bg-pink-100 text-pink-500 group-hover:from-pink-100 group-hover:to-pink-200'
  };
</script>

<button
  class="group flex rounded items-center justify-center gap-2 w-fit overflow-hidden text-sm pr-2 whitespace-nowrap bg-white hover:bg-gradient-to-b hover:from-white hover:to-gray-100 text-gray-500 border border-gray-300"
  on:click
>
  <div class="flex justify-center items-center h-6 w-full px-2 group-hover:bg-gradient-to-b transition-colors {colorClasses[color]}">
    <svelte:component this={icon} class="h-4 w-4" />
  </div>
  <slot />
</button>