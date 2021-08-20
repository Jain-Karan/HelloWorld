<svelte:head>
	<link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
</svelte:head>
  <style>
    body {
    min-width: 60em;
  }
  .column {
    width: 20em;
    float: left;
    padding-bottom: 100px;
		border:3px solid black;
		margin:2em;
  }
  .portlet {
    margin: 0 1em 1em 0;
    padding: 0.3em;
  }
  .portlet-header {
    padding: 0.2em 0.3em;
    margin-bottom: 0.5em;
    position: relative;
  }
  .portlet-toggle {
    position: absolute;
    top: 50%;
    right: 0;
    margin-top: -8px;
  }
  .portlet-content {
    padding: 0.4em;
  }
  .portlet-placeholder {
    border: 1px dotted black;
    margin: 0 1em 1em 0;
    height: 50px;
  }
</style>
<script>
  jQuery( function() {
    jQuery( ".column" ).sortable({
      connectWith: "div[data-type$='list']",
      handle: ".portlet-header",
      cancel: ".portlet-toggle",
      placeholder: "portlet-placeholder ui-corner-all"
    });
 
    jQuery( ".portlet" )
      .addClass( "ui-widget ui-widget-content ui-helper-clearfix ui-corner-all" )
      .find( ".portlet-header" )
        .addClass( "ui-widget-header ui-corner-all" )
        .prepend( "<span class='ui-icon ui-icon-minusthick portlet-toggle'></span>");
 
    jQuery( ".portlet-toggle" ).on( "click", function() {
      var icon = jQuery( this );
      icon.toggleClass( "ui-icon-minusthick ui-icon-plusthick" );
      icon.closest( ".portlet" ).find( ".portlet-content" ).toggle();
    });
  } );
</script>
<div data-type="rowlist" class="column" id="dimensionstable">
 
  <div class="portlet">
    <div class="portlet-header">Feeds</div>
    <div class="portlet-content">Lorem ipsum dolor sit amet, consectetuer adipiscing elit</div>
  </div>
 
  <div class="portlet">
    <div class="portlet-header">News</div>
    <div class="portlet-content">Lorem ipsum dolor sit amet, consectetuer adipiscing elit</div>
  </div>
 
</div>
 
<div data-type="collist" class="column" id ="rowstable">
 
  <div class="portlet">
    <div class="portlet-header">Shopping</div>
    <div class="portlet-content">Lorem ipsum dolor sit amet, consectetuer adipiscing elit</div>
  </div>
 
</div>
 
<div data-type="dimlist" class="column" id="columnstable">
 
  <div class="portlet">
    <div class="portlet-header">Links</div>
    <div class="portlet-content">Lorem ipsum dolor sit amet, consectetuer adipiscing elit</div>
  </div>
 
  <div class="portlet">
    <div class="portlet-header">Imags</div>
    <div class="portlet-content">Lorem ipsum dolor sit amet, consectetuer adipiscing elit</div>
  </div>
 
</div>