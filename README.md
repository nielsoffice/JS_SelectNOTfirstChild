# JS_SelectNOTfirstChild
javaScript select not first child / jQuery 


```JS
jQuery(() => {
	
 const selectNotFirst = function( objectElem = {} ) {
	
  this.target = objectElem;	 
	 
 }	

 selectNotFirst.prototype.insertClass = function( $class ) {
   return $class;
 }

 selectNotFirst.prototype.init = function() {
	
  let objectData  = this.target;
  let __dataID    = objectData.ID;
  let __dataClass = objectData.class;
  let __targetID  = jQuery(__dataID).children(); //.not(':first');
  let __notLast	  = __targetID.splice(1, 9);

  let __insertClass = selectNotFirst.prototype.insertClass( __dataClass );

	__notLast.forEach(function( v ) { 
		
	  let ID = '#'+ v.id; jQuery(ID).addClass(__insertClass);	
		
	});
	 
 }	
 	
 // init 
 const __notFirst = function( oe ) { const Success = new selectNotFirst( oe ); Success.init(); }
 
 // USAGE:  
 __notFirst({ ID : '#_dynamic_list-55-2184', class: 'notFirstChild' });
 
});

```
