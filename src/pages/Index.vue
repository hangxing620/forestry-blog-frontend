<template>
	<Layout>
		<div id="container">
			<Hero />
			<ProjectsGrid :projects="$page.projects.edges" />
		</div>
		<LatestJournals :journals="$page.journals.edges" />
	</Layout>
</template>

<page-query>
query {
  projects: allStrapiProject {
    edges {
      node {
        id
        date (format: "YYYY")
        title
        categories {
          title
        }
        thumbnail {
          url (quality: 90)
        }
      }
    }
  }
	journals: allStrapiJournal {
    edges {
      node {
        id
        title
      }
    }
  }
}
</page-query>

<script>
import Hero from "@/components/Hero"
import ProjectsGrid from "@/components/ProjectsGrid"
import LatestJournals from "@/components/LatestJournals"
export default {
	components: {
		Hero,
		ProjectsGrid,
		LatestJournals
	}
};
</script>

<style>
.home-links a {
	margin-right: 1rem;
}
</style>
