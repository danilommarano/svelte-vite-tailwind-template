<script lang="ts">
  import { SvelteComponent } from 'svelte';
  import { tailwind_bg_colors } from '../utils/bgColors.ts'
  import { tailwind_border_colors } from '../utils/borderColors.ts'
  import { tailwind_text_colors } from '../utils/textColors.ts'

  export let color: string;
  export let radious: 'normal' | 'full' = 'normal';
  export let intensity: number = 50;

  let buttonHeight: 'h-6';
  let textSize = 'text-sm'
  let xPadding = 'px-2'
  let borderRadious: string;
  let bgColor: string;
  let textColor: string;
  let borderColor: string;
  
  if (color !== 'white' && color !== 'black') {
      bgColor = 'bg-white';
      borderColor = 'border ' + tailwind_border_colors[color][500];
      textColor = 'border ' + tailwind_text_colors[color][500];
  }
  else {
      bgColor = tailwind_bg_colors[color];
      borderColor = 'border ' + tailwind_border_colors['gray'][300];
  }

  if (radious == 'normal') {
      borderRadious = 'rounded'
  }
  else if (radious == 'full') {
      borderRadious = 'rounded-full'
  }

  let buttonClass = (
      'flex items-center justify-center gap-2 w-fit' + ' ' +
      buttonHeight + ' ' +
      xPadding + ' ' +
      textSize + ' ' + ' ' +
      borderRadious + ' ' + 
      bgColor + ' ' +
      borderColor + ' ' +
      textColor + ' ' + 
      ''
  )

</script>


<button class={buttonClass} on:click>
    <slot />
</button>

