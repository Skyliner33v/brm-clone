<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :clipped="clipped"
      fixed
      app
      width="325"
    >
      <a :href="'//' + aashtoURL" target="_blank">
        <v-img
          src="/aashtoBridge.png"
          contain
          aspect-ratio="2.5"
          width="250"
          class="mt-2"
        ></v-img>
      </a>
      <v-list>
        <v-list-item to="/" active-class="blue-grey darken-3">
          <v-icon class="pr-8 pl-1">mdi-home</v-icon>
          <v-list-item-content>
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-list>
        <v-list-group
          v-for="item in items"
          :key="item.title"
          :prepend-icon="item.icon"
          active-class="blue-grey darken-3 white--text"
        >
          <template v-slot:activator>
            <v-list-item-content>
              <v-list-item-title v-text="item.title"></v-list-item-title>
            </v-list-item-content>
          </template>

          <v-list-item
            v-for="subItem in item.items"
            :key="subItem.title"
            :to="subItem.to"
            active-class="blue-grey darken-3 white--text"
          >
            <v-list-item-content align="left">
              <v-list-item-title
                v-text="subItem.title"
                class="pl-2"
              ></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-group>
      </v-list>
      <v-spacer />
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <a :href="'//' + mayvueURL" target="_blank" class="mr-n12">
        <v-img src="/mayvueLogo.png" contain max-height="50"></v-img>
      </a>
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app class="d-flex flex-row-reverse">
      <span
        >&copy; American Association of State Highway and Transportation
        Officials. All Rights Reserved</span
      >
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: true,
      fixed: false,
      title: 'AASHTOware Bridge Management',
      aashtoURL: 'www.aashtowarebridge.com',
      mayvueURL: 'www.mayvue.com',
      items: [
        {
          icon: 'mdi-bridge',
          title: 'Bridges',
          items: [
            { title: 'View List', to: '/bridges/list' },
            { title: 'Manage Layouts', to: '/bridges/manage-layout' },
            { title: 'Manage Filters', to: '/bridges/manage-filter' },
            { title: 'New Inspection', to: '/bridges/new-inspection' },
            { title: 'Sufficiency Rating', to: '/bridges/suff-rating' },
            { title: 'Validate', to: '/bridges/validate' },
            { title: 'Create Structure', to: '/bridges/create-structure' },
            { title: 'Copy Structure', to: '/bridges/copy-structure' },
            { title: 'Remove Structure', to: '/bridges/remove-structure' },
            {
              title: 'Manage Bridge Groups',
              to: '/bridges/manage-groups'
            },
            { title: 'Mapping', to: '/bridges/mapping' }
          ]
        },
        {
          icon: 'mdi-subway',
          title: 'Tunnels',
          items: [
            { title: 'Tunnel List', to: '/tunnels/list' },
            { title: 'Tunnel Inspection', to: '/tunnels/inspection' },
            { title: 'Tunnel Inventory', to: '/tunnels/inventory' }
          ]
        },
        {
          icon: 'mdi-chart-line',
          title: 'Reports',
          items: [
            { title: 'Generate', to: '/reports/generate' },
            { title: 'Register', to: '/reports/register' }
          ]
        },
        {
          icon: 'mdi-settings',
          title: 'Admin',
          items: [
            { title: 'Security', to: '/admin/security' },
            { title: 'General Config', to: '/admin/config' },
            { title: 'Mapping', to: '/admin/mapping' },
            { title: 'Modeling Config', to: '/admin/model-config' },
            { title: 'Tunnels', to: '/admin/tunnels' }
          ]
        },
        {
          icon: 'mdi-clipboard-text',
          title: 'Inspection',
          items: [
            { title: 'Condition', to: '/inspection/condition' },
            { title: 'Appraisal', to: '/inspection/appraisal' },
            { title: 'Inventory', to: '/inspection/inventory' },
            { title: 'Schedule', to: '/inspection/schedule' },
            { title: 'Work', to: '/inspection/work' },
            { title: 'Multimedia', to: '/inspection/multimedia' },
            { title: 'Assessments', to: '/inspection/assessments' },
            { title: 'Load Ratings', to: '/inspection/load-rating' },
            {
              title: 'Element Condition Rating',
              to: '/inspection/elem-cond-rating'
            },
            { title: 'Cross Sections', to: '/inspection/cross-section' }
          ]
        },
        {
          icon: 'mdi-clipboard-flow',
          title: 'Gateway',
          items: [
            { title: 'Export', to: '/gateway/export' },
            { title: 'Import', to: '/gateway/import' },
            { title: 'Check Out', to: '/gateway/check-out' },
            { title: 'Check In', to: '/gateway/check-in' },
            { title: 'Override', to: '/gateway/override' },
            { title: 'Tunnels', to: '/gateway/tunnel' }
          ]
        },
        {
          icon: 'mdi-file-chart',
          title: 'Analysis',
          items: [
            { title: 'Work Candidates', to: '/analysis/work-candidate' },
            { title: 'Utility Value', to: '/analysis/utility-value' },
            { title: 'LCCA', to: '/analysis/lcca' }
          ]
        },
        {
          icon: 'mdi-file-multiple',
          title: 'Projects',
          items: [
            { title: 'Project List', to: '/projects/list' },
            { title: 'Manage Layouts', to: '/projects/layout' },
            { title: 'Manage Filters', to: '/projects/filter' },
            { title: 'Create/Edit Project', to: '/projects/create-edit' },
            { title: 'Upload Project', to: '/projects/upload' },
            { title: 'Combine Projects', to: '/projects/combine' },
            { title: 'Split Project', to: '/projects/split' },
            { title: 'Manage Funding', to: '/projects/funding' }
          ]
        },
        {
          icon: 'mdi-file',
          title: 'Programs',
          items: [
            { title: 'Program List', to: '/programs/list' },
            { title: 'Create/Edit Programs', to: '/programs/create-edit' },
            { title: 'Assign Projects', to: '/programs/assign' },
            {
              title: 'Performance Measures',
              to: '/programs/performance-measures'
            },
            { title: 'Funding Allocation', to: '/programs/funding-allocation' },
            { title: 'Program Planning', to: '/programs/planning' },
            { title: 'Program Results', to: '/programs/results' },
            { title: 'Executive Summary', to: '/programs/executive-summary' },
            { title: 'Create/Edit Scenarios', to: '/scenarios/create-edit' },
            { title: 'Scenario Explorer', to: '/scenario/explorer' },
            { title: 'Program Comparison', to: '/scenario/comparison' }
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
span {
  font-size: 12px;
}
</style>
