<template>
  <div>

		<!--CARDS WRAPPER-->
    <section class="uk-section uk-section-small uk-section-default uk-padding-remove-bottom">

      <div class="uk-container uk-container-expand uk-margin-large-bottom">
				<ul class="uk-subnav uk-subnav-pill">
					<li class="uk-active" uk-filter-control><a href="#">Show All</a></li>
					<li uk-filter-control=".nature-card"><a href="#">Nature</a></li>
					<li uk-filter-control=".music-card"><a href="#">Music</a></li>
					<li uk-filter-control=".photo-card"><a href="#">Photography</a></li>
					<li uk-filter-control=".design-card"><a href="#">Design</a></li>
				</ul>

        <!-- <input type="search" v-model="q" @input="$fetch" /> -->

        <!-- <div class="uk-inline uk-width-1-1">
          <span class="uk-form-icon uk-form-icon-flip" uk-icon="icon: search"></span>
          <input class="uk-input uk-width-1-1 search-fld" type="search" placeholder="Type your search" autofocus v-model="q" @input="$fetch">
          <a href="#" class="search-filter" uk-filter-control="[data-tags*='']" hidden>Search</a>
        </div>

        <div class="spacer"></div> -->

    <div class="uk-grid uk-grid-medium uk-child-width-1-2@s uk-child-width-1-3@m uk-child-width-1-4@l  uk-child-width-1-5@xl uk-grid-match js-filter" uk-grid="masonry: true" uk-sortable="handle: .drag-icon">

      <!-- card -->
					<div v-for="(post, index) in posts" :key="index" :class="post.category" :data-tags="post.title.toLowerCase()">
						<div class="uk-card uk-card-small uk-card-default">
							<div class="uk-card-header">
								<div class="uk-grid uk-grid-small uk-text-small" uk-grid>
									<div class="uk-width-expand">
										<span class="cat-txt">{{post.category}}</span>
									</div>
									<div class="uk-width-auto uk-text-right uk-text-muted">
										<span uk-icon="icon:clock; ratio: 0.8" uk-tooltip="Last Update"></span> {{ $moment(post.updatedAt).fromNow()}}
									</div>
								</div>
							</div>
							<div class="uk-card-media">
								<div class="uk-inline-clip uk-transition-toggle" tabindex="0">
									<img class="lazy" :data-src="post.image" data-width="400" data-height="300" uk-img alt="" src="img/transp.gif">
									<div class="uk-transition-slide-bottom uk-position-bottom uk-overlay uk-overlay-primary">
										<span uk-icon="icon:heart; ratio: 0.8"></span> 12.345 <span uk-icon="icon:comment; ratio: 0.8"></span> 12.345
									</div>
								</div>

							</div>
							<div class="uk-card-body">
								<h6 class="uk-margin-small-bottom uk-margin-remove-adjacent uk-text-bold"><a :href="post.slug">{{ post.title }}</a></h6>
								<p class="uk-text-small uk-text-muted">{{ $moment(post.posted, 'DD/MM/YYYY').format('MMMM Do YYYY') }}</p>
							</div>
							<div class="uk-card-footer">
								<div class="uk-grid uk-grid-small uk-grid-divider uk-flex uk-flex-middle" uk-grid>
									<div class="uk-width-expand uk-text-small">
										{{post.author}}
									</div>
									<div class="uk-width-auto uk-text-right">
										<a href="#" uk-tooltip="title: Twitter" class="uk-icon-link" uk-icon="icon:twitter; ratio: 0.8"></a>
										<a href="#" uk-tooltip="title: Instagram" class="uk-icon-link" uk-icon="icon:instagram; ratio: 0.8"></a>
										<a href="#" uk-tooltip="title: Behance" class="uk-icon-link" uk-icon="icon:behance; ratio: 0.8"></a>
										<a href="#" uk-tooltip="title: Pinterest" class="uk-icon-link" uk-icon="icon:pinterest; ratio: 0.8"></a>
									</div>
									<div class="uk-width-auto uk-text-right">
										<a uk-tooltip="title: Drag this card" href="#" class="uk-icon-link drag-icon" uk-icon="icon:move; ratio: 1"></a>
									</div>
								</div>
							</div>
						</div>
					</div>
					<!-- /card -->

    </div>

      </div>

    </section>

    <!-- <pre>{{ posts }}</pre> -->

  </div>
</template>
<script>


export default {

  data() {
    return {
      posts: [],
      q: ''
    }
  },
  async fetch() {
    this.posts = await this.$content('posts')
    .sortBy('title', 'desc')
    .search(this.q)
    .fetch()
  },
  methods: {
    async onSearch($event) {
      this.q = $event.target.value;

      this.posts = await this.$content('posts')
      .search(this.q)
      .sortBy('title', 'desc')
      .fetch()
    }
  }
}
</script>
