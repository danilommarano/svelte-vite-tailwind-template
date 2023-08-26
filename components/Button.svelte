<script lang="ts">
  import { SvelteComponent } from 'svelte';
  import { TailwindBackgroundColors } from '../utils/TailwindBackgroundColors'
  import { TailwindBorderColors } from '../utils/TailwindBorderColors'

  export let size: 'tiny' | 'small' | 'base' | 'large' | 'giant' = 'base';
  export let radious: 'normal' | 'full' = 'normal';
  export let color: string;
  export let intensity: number = 500;

  const sizes = {
    tiny: { height: 'h-6', textSize: 'text-sm', xPadding: 'px-2' },
    small: { height: 'h-7', textSize: 'text-sm', xPadding: 'px-2' },
    base: { height: 'h-8', textSize: 'text-base', xPadding: 'px-3' },
    large: { height: 'h-9', textSize: 'text-base', xPadding: 'px-4' },
    giant: { height: 'h-10', textSize: 'text-lg', xPadding: 'px-5' }
  };

  let { height: buttonHeight, textSize, xPadding } = sizes[size];
  let yPadding = ''; // Define yPadding here if needed
  let borderRadious = radious === 'normal' ? 'rounded' : 'rounded-full';

  let bgColor, borderColor;
  if (color !== 'white' && color !== 'black') {
    bgColor = TailwindBackgroundColors[color][intensity];
    borderColor = 'border ' + TailwindBorderColors[color][intensity];
  } else {
    bgColor = TailwindBackgroundColors[color];
    borderColor = 'border ' + TailwindBorderColors['gray'][300];
  }

  let buttonClass = `
    flex items-center justify-center gap-2 w-fit
    ${buttonHeight} ${xPadding} ${yPadding} ${textSize} ${borderRadious}
    ${bgColor} ${borderColor}
  `;
</script>

<button class={buttonClass} on:click>
  <slot />
</button>
