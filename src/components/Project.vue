<template>
    <div class="card">
        <div class="header">
            <h3>{{ title }}</h3>
        </div>
        
        <div class="content">
            <slot></slot>
        </div>

        <div v-if="showReadMore" class="read-more">
            Read more
        </div>
        
        <div v-if="showFooter" class="footer">
            <span v-for="t in technologies" :key="t" class="skill">{{ t }}</span>
        </div>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Project extends Vue {
    @Prop() private title!: string;
    @Prop() private technologies!: string[];
    @Prop() private showReadMore!: boolean;

    get showFooter() {
        return this.technologies.length > 0
    }
}
</script>