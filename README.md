# README

Things you may want to cover:
  * Ruby version
  * System dependencies
  * Configuration
  * Database creation
  * Database initialization
  * How to run the test suite
  * Services (job queues, cache servers, search engines, etc.)
  * Deployment instructions


AJAX stands for Asynchronous JavaScript and XML. Ajax is not a single technology; it is a suite of several technologies. Ajax incorporates the following −

  * XHTML for the markup of web pages
  * CSS for the styling
  * Dynamic display and interaction using the DOM
  * Data manipulation and interchange using XML
  * Data retrieval using XMLHttpRequest
  * JavaScript as the glue that meshes all this together


`Rails new ponies // create rails app`
`cd ponies`
`rails generate scaffold Pony name:string profession:string` // generates the scaffold with name and profession column
`rake db:migrate` // scaffold crée des models... rails db:migrate crée la bdd correspondante

`rails s`

http://localhost:3000/ponies/new
// Formulaire New Pony
Name :
Profession :
Create Pony
Back

macbook:ponies admin$ rails routes
   Prefix Verb   URI Pattern                Controller#Action
   ponies GET    /ponies(.:format)          ponies#index
          POST   /ponies(.:format)          ponies#create
 new_pony GET    /ponies/new(.:format)      ponies#new
edit_pony GET    /ponies/:id/edit(.:format) ponies#edit
     pony GET    /ponies/:id(.:format)      ponies#show
          PATCH  /ponies/:id(.:format)      ponies#update
          PUT    /ponies/:id(.:format)      ponies#update
          DELETE /ponies/:id(.:format)      ponies#destroy
# 
# Creating an Ajax
app/views/ponies/index.html.erb
Update your destroy line with : `, :remote => true, :class => 'delete_pony'` (add)
`$('.delete_pony').bind('ajax:success', function() {
   $(this).closest('tr').fadeOut();
});`

Open your controller file (app/controllers/ponies_controller.rb)=; add the following code in destroy method :
`# DELETE /ponies/1
# DELETE /ponies/1.json
def destroy
   @pony = Pony.find(params[:id])
   @pony.destroy
   
   respond_to do |format|
      format.html { redirect_to ponies_url }
      format.json { head :no_content }
      format.js   { render :layout => false }
   end
   
end`

qmslfqmlqsjdmqlkjdf qmdkj
