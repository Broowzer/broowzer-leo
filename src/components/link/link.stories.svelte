<script>
  import { Meta, Story, Template } from '@storybook/addon-svelte-csf'
  import {
    getNonStyleArgs,
    getStyleFromArgs
  } from '../../../.storybook/argHelper'

  import Link from './link.svelte'
</script>

<Meta
  title="Link"
  component={Link}
  argTypes={{
    href: {
      control: 'text',
      description: 'The href for the link',
      type: 'string',
      defaultValue: 'https://.com'
    },
    target: {
      control: 'text',
      description: 'The target for the link',
      type: 'string',
      defaultValue: '_blank'
    },
    text: {
      control: 'text',
      description: 'The text content of the link',
      type: 'string',
      defaultValue: 'Download '
    },
    '--leo-link-color': {
      type: 'string',
      control: 'color',
      description: 'The color of the link'
    },
    '--leo-link-hover-color': {
      type: 'string',
      control: 'color',
      description: 'The hover color of the link'
    },
    '--leo-link-visited-color': {
      type: 'string',
      control: 'color',
      description: 'The visited color of the link'
    },
    '--leo-link-disabled-color': {
      type: 'string',
      control: 'color',
      description: 'The disabled color of the link'
    },
    '--leo-link-focus-color': {
      type: 'string',
      control: 'color',
      description:
        'The focused color of the link. Defaults to the link color, if not set'
    },
    '--leo-link-focus-shadow': {
      type: 'text',
      control: 'string',
      description: 'The focused shadow for the link'
    }
  }}
/>

<Template let:args>
  <div style={getStyleFromArgs(args)}>
    <Link href="#foo" {...getNonStyleArgs(args)} />
  </div>
</Template>

<Story name="Default" />
