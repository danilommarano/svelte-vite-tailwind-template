<script lang="ts">
  import { SvelteComponent } from 'svelte';
  import { tailwind_bg_colors } from '../utils/bgColors.ts'
  import { tailwind_border_colors } from '../utils/borderColors.ts'

  export let size: 'tiny' | 'small' | 'base' | 'large' | 'giant' = 'base';
  export let radious: 'normal' | 'full' = 'normal';
  export let color: string;
  export let intensity: number = 500;

  let buttonHeight: string;
  let textSize: string;
  let xPadding: string;
  let yPadding: string;
  let bgColor: string;
  let borderColor: string;
  let borderRadious: string;

  if (size == 'tiny') {
      buttonHeight = 'h-6'
      textSize = 'text-sm'
      xPadding = 'px-2'
  }
  else if (size == 'small') {
      buttonHeight = 'h-7'
      textSize = 'text-sm'
      xPadding = 'px-2'
  }
  else if (size == 'base') {
      buttonHeight = 'h-8'
      textSize = 'text-base'
      xPadding = 'px-3'
  }
  else if (size == 'large') {
      buttonHeight = 'h-9'
      textSize = 'text-base'
      xPadding = 'px-4'
  }
  else if (size == 'giant') {
      buttonHeight = 'h-10'
      textSize = 'text-lg'
      xPadding = 'px-5'
  }

  if (radious == 'normal') {
      borderRadious = 'rounded'
  }
  else if (radious == 'full') {
      borderRadious = 'rounded-full'
  }

  if (color !== 'white' && color !== 'black') {
      bgColor = tailwind_bg_colors[color][intensity];
      borderColor = 'border ' + tailwind_border_colors[color][intensity];
  }
  else {
      bgColor = tailwind_bg_colors[color];
      borderColor = 'border ' + tailwind_border_colors['gray'][300];
  }

  let buttonClass = (
      'flex items-center justify-center gap-2 w-fit' + ' ' +
      buttonHeight + ' ' +
      xPadding + ' ' +
      yPadding + ' ' + 
      textSize + ' ' + ' ' +
      borderRadious + ' ' + 
      bgColor + ' ' +
      borderColor + ' ' +
      ''
  )

</script>


<button class={buttonClass} on:click>
    <slot />
</button>

