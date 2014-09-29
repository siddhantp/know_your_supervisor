$(document).ready(function(){
	var supervisors=[];
	var app={
		init:function() {
			this.url='http://data.sfgov.org/resource/ujme-i5np.json';
			this.fetch();
		},
		fetch:function(){
			$.getJSON(this.url,function(data){
				for(var current_district=1;current_district<=11;current_district++){
					for(i in data) {
						if(data[i].district==current_district) {
							supervisors.push({
								district:data[i].district,
								name:data[i].name,
								address:data[i].address,
								phone:data[i].phone.phone_number,
								email:data[i].email,
								website:data[i].website.url,
								facebook:data[i].facebook.url,
								twitter:data[i].twitter
							});
							break;
						}	
					};
				};
				var template=Handlebars.compile($('#supervisor-template').html());
				var table_template=Handlebars.compile($('#supervisor-info-template').html());
				$('#supervisors-list').append(template(supervisors));
				$('#supervisors-info').append(table_template(supervisors));
				$('#supervisors-listview').listview();
			});		
		}
	};
	app.init();

	$(document).ajaxStart(function () {
	    $("#loading").show();
	});

	$(document).ajaxComplete(function () {
	    $("#loading").hide();
	});

	$(document).on('click','#supervisors-listview li',function(){
		sid='#'+$(this).data('sid');
		console.log(sid);
		$('#supervisors-list').hide();
		$('#supervisors-info').show();
		$(sid).show();
	});
	
	$('#back-btn').click(function(){
		$('.supervisor-info-table').hide();
		$('#supervisors-info').hide();
		$('#supervisors-list').show();
	});
});
