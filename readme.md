Custom Additions:

[code]
page: tmpl/single-tmpl.php
replace:
<?php if( get_post_format() ) { get_template_part('parts/post-formats'); } ?>

with:
      <?php if( get_post_format() ){
 		get_template_part('parts/post-formats');
	 }else{
?>
  <div class="page-image">
  	<div class="image-container">
  		<?php hu_the_post_thumbnail('thumb-large', '', false );//no attr and no placeholder ?>
  		<?php
  			$caption = get_post(get_post_thumbnail_id())->post_excerpt;
  			$description = get_post(get_post_thumbnail_id())->post_content;
  			echo '<div class="page-image-text">';
  			if ( isset($caption) && $caption ) echo '<div class="caption">'.$caption.'</div>';
  			if ( isset($description) && $description ) echo '<div class="description"><i>'.$description.'</i></div>';
  			echo '</div>';
  		?>
  	</div>
  </div><!--/.page-image-->
<?php	
}
	 ?>
[/code]
