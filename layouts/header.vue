<template>
  <!--HEADER-->
		<header id="site-head">
			<div class="uk-container uk-container-expand">
				<div class="uk-grid uk-grid-medium uk-flex uk-flex-middle" data-uk-grid>
					<div class="uk-width-auto">
						<a href="/" class="uk-logo" title=""><img src="/assets/img/logo.svg" alt=""></a>
					</div>
					<div class="uk-width-expand">
            <!-- <input class="uk-input uk-width-1-1 search-fld" type="search" placeholder="Type your search" autofocus v-model="q" @input="$emit('q', $event)"> -->
            <form id="search-form" action="">
							<div class="uk-inline uk-width-1-1">
								<span class="uk-form-icon uk-form-icon-flip" data-uk-icon="icon: search"></span>
								<input class="uk-input uk-width-1-1 search-fld" type="text" placeholder="Type your search" autofocus>
								<a href="#" class="search-filter" data-uk-filter-control="[data-tags*='']" hidden>Search</a>
							</div>
						</form>
					</div>
					<div class="uk-width-auto">
						<ul class="uk-subnav" data-uk-margin>
							<li class="uk-visible@s"><a href="#">Home</a></li>
							<li class="uk-visible@s"><a href="#">About Us</a></li>
							<li class="uk-visible@s">
								<a href="#" data-uk-icon="icon:comments"></a>
								<div class="drop-nav drop-comments uk-dropdown" data-uk-dropdown="mode: click; offset: 20;animation: uk-animation-slide-bottom-small; duration: 150">
									<ul class="uk-child-width-expand" data-uk-tab="animation: uk-animation-fade">
										<li><a href="#">Your Messages</a></li>
										<li><a href="#">Activity</a></li>
									</ul>
									<ul class="uk-switcher uk-margin">
										<li class="uk-height-small uk-overflow-auto">
											<div class="message">
												Excepteur sint occaecat cupidatat non
												proident, sunt in culpa qui officia deserunt mollit anim id est laborum...<a href="" class="uk-link">VIEW MESSAGE</a>
											</div>
											<div class="message">
												Excepteur sint occaecat cupidatat non
												proident, sunt in culpa qui officia deserunt mollit anim id est laborum...<a href="" class="uk-link">VIEW MESSAGE</a>
											</div>
											<div class="message">
												Excepteur sint occaecat cupidatat non
												proident, sunt in culpa qui officia deserunt mollit anim id est laborum...<a href="" class="uk-link">VIEW MESSAGE</a>
											</div>
											<div class="message">
												Excepteur sint occaecat cupidatat non
												proident, sunt in culpa qui officia deserunt mollit anim id est laborum...<a href="" class="uk-link">VIEW MESSAGE</a>
											</div>
										</li>
										<li>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</li>
									</ul>
								</div>
							</li>
							<li class="uk-visible@s">
								<a href="#" data-uk-icon="icon:more"></a>
								<div class="drop-nav uk-dropdown" data-uk-dropdown="mode: click; offset: 20;animation: uk-animation-slide-bottom-small; duration: 150">
									<h4 class="uk-margin-small-bottom uk-margin-remove-adjacent">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</h4>
									<p class="uk-text-small uk-text-muted">Excepteur sint occaecat cupidatat non
									proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
									<hr>
									<a href="#" class="uk-button uk-button-primary uk-width-1-1">UPDATE YOUR ACCOUNT</a>
									<hr>
									<ul class="uk-nav-default uk-nav-parent-icon" data-uk-nav>
										<li class="uk-nav-header">Header</li>
										<li><a href="#"><span class="uk-margin-small-right" data-uk-icon="icon: table"></span> Item</a></li>
										<li><a href="#"><span class="uk-margin-small-right" data-uk-icon="icon: thumbnails"></span> Item</a></li>
										<li class="uk-nav-divider"></li>
										<li><a href="#"><span class="uk-margin-small-right" data-uk-icon="icon: trash"></span> Item</a></li>
									</ul>
								</div>
							</li>
							<li class="uk-hidden@s"><a data-uk-navbar-toggle-icon data-uk-toggle href="#offcanvas-nav"></a></li>
						</ul>
					</div>
				</div>
			</div>
		</header>
		<!--/HEADER-->
</template>
<script>
export default {
  props: [ 'q' ]
}
</script>
