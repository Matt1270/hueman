Custom Additions:

```
page: tmpl/single-tmpl.php
replace:
<?php if( get_post_format() ) { get_template_part('parts/post-formats'); } ?>

with:
      <?php if( get_post_format() ){
 		get_template_part('parts/post-formats');
	 }else{
?>
  <div class="image-container">
  			<?php if ( has_post_thumbnail() ) {
  				hu_the_post_thumbnail('thumb-large', '', false);//no attr, no placeholder
  				$caption = get_post(get_post_thumbnail_id())->post_excerpt;
  				if ( isset($caption) && $caption ) echo '<div class="image-caption">'.$caption.'</div>';
  			} ?>
  		</div>
<?php	
}
	 ?>
```
