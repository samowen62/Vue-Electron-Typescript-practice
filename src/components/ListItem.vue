<template>
    <li>
      <a :href="link" target="_blank" rel="noopener" 
            @mouseover="onHover"  @mouseleave="onLeave"  :style="listStyle">{{text}}
        </a>
    </li>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class ListItem extends Vue {
  @Prop() private link!: string;
  @Prop() private text!: string;
  @Prop() private hovering: boolean = false;

  onHover (): void {
    this.hovering = true;
  }
  onLeave(): void{
      this.hovering = false;
  }

  get listStyle(){
      return this.hovering ? "color:red " : "color:green";
  }
}
</script>


