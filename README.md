# add-to-cart


     {% comment %}
        <!--  Polishing Packaging products code start  -->

            {% if product.metafields.custom.polishing_cloth != blank %}
            {% assign products = product.metafields.custom.polishing_cloth.value %}
         {%- for product in products -%}
              <div class="question_custom_gift">
            <input type="checkbox"  class="polishing_cloth" value="{{ product.variants.first.id}}">
            <label for="vehicle1">Add Polishing cloth</label>
              </div>  
            {% endfor %}
                 <div class="custom_product_meta" style="display:none;">
                <h3 class="complementary_section_title">{{ section.settings.heading_custom }}<span>
              <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" 
              width="40" zoomAndPan="magnify" viewBox="0 0 30 30.000001" height="40" preserveAspectRatio="xMidYMid meet" 
              version="1.0"><defs><clipPath id="id1">
           <path d="M 2.847656 4.792969 L 26.796875 4.792969 L 26.796875 24.390625 L 2.847656 24.390625 Z M 2.847656 4.792969 " clip-rule="nonzero"/></clipPath></defs><g clip-path="url(#id1)"><path fill="rgb(0%, 0%, 0%)" d="M 11.078125 24.3125 L 2.847656 15.890625 L 6.128906 12.53125 L 11.078125 17.597656 L 23.519531 4.875 L 26.796875 8.230469 Z M 11.078125 24.3125 " fill-opacity="1" fill-rule="nonzero"/></g></svg></span></h3>
              <ul class="complementey_slider">
        {%- for product in products -%}
          <li class="meta_product_item" item_id="{{ product.id }}">
            <div class="content-all-customm">
            <div class="meta_container">
              <div class="image-left">
          {% if product.featured_image != blank %}
              <div class="meta-item-image">
              <img src="{{ product.featured_image | img_url:'87x87' }}" meta_id ="{{ product.variants.id }}" alt="" loading="lazy" width="100" height="100">
              </div>
            {% endif %}
              </div>
              <div class="info-right">
              <div class="meta-item-title">{{ product.title }}</div>  
             <div class="meta-item-price">
               {% if product.compare_at_price_min > product.price %}<span>{{ product.compare_at_price_min  | money_with_currency }}</span>{% endif %}{{ product.price | money_with_currency }}
             </div> 
            </div>
              
            </div>
            </div>
              </li>
          {%- endfor -%}
              </ul>
                </div>
                 {% endif %}
            <!--  Polishing Packaging products code end  -->

            <!--  Gift Packaging products code start  -->
            
            {% if product.metafields.custom.gift_wrap != blank %}
            {% assign productss = product.metafields.custom.gift_wrap.value %}
         {%- for productt in productss -%}
              <div class="question_custom_gifts">
            <input type="checkbox" class="gift_cart" value="{{ productt.variants.first.id}}">
            <label for="vehicle1">Add Gift Card</label>
              </div>  
            {% endfor %}
                 <div class="custom_product_metas" style="display:none;">
                <h3 class="complementary_section_title">Gift Card Added<span>
              <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" 
              width="40" zoomAndPan="magnify" viewBox="0 0 30 30.000001" height="40" preserveAspectRatio="xMidYMid meet" 
              version="1.0"><defs><clipPath id="id1">
           <path d="M 2.847656 4.792969 L 26.796875 4.792969 L 26.796875 24.390625 L 2.847656 24.390625 Z M 2.847656 4.792969 " clip-rule="nonzero"/></clipPath></defs><g clip-path="url(#id1)"><path fill="rgb(0%, 0%, 0%)" d="M 11.078125 24.3125 L 2.847656 15.890625 L 6.128906 12.53125 L 11.078125 17.597656 L 23.519531 4.875 L 26.796875 8.230469 Z M 11.078125 24.3125 " fill-opacity="1" fill-rule="nonzero"/></g></svg></span></h3>
              <ul class="complementey_slider">
        {%- for productt in productss -%}
          <li class="meta_product_item" item_id="{{ productt.id }}">
            <div class="content-all-customm">
            <div class="meta_container">
              <div class="image-left">
          {% if productt.featured_image != blank %}
              <div class="meta-item-image">
              <img src="{{ productt.featured_image | img_url:'87x87' }}" meta_id ="{{ productt.variants.id }}" alt="" loading="lazy" width="100" height="100">
              </div>
            {% endif %}
              </div>
              <div class="info-right">
              <div class="meta-item-title">{{ productt.title }}</div>  
             <div class="meta-item-price">
               {% if productt.compare_at_price_min > productt.price %}<span>{{ productt.compare_at_price_min  | money_with_currency }}</span>{% endif %}{{ productt.price | money_with_currency }}
             </div> 
            </div>
              
            </div>
            </div>
              </li>
          {%- endfor -%}
              </ul>
                </div>
                 {% endif %}
            <!--  Gift Packaging products code end  -->
            {% endcomment %}



              // Product page gift warraping js
  $(document).on("click", ".question_custom_gifts", function(e) {
       var checked = $(this).find("input:checkbox").is(":checked");
       if (checked) {
         // show gift packing product
          $('.custom_product_metas').show(200);
         // get product id
          var pr_ID = $('input:checkbox').attr('value');
         // add product on cart
//          $(document).one("click", ".custom_cart_btnns", function() {
//            var count = $('.cart-count-bubble span').html();
//            // alert(count);
//           setTimeout(function() {
//            $.ajax({ 
//           type: 'POST',
//           url: '/cart/add.js',
//           data: {
//           quantity:1,
//           id: pr_ID
//            },
//          dataType: 'json',
//          success: function() {
//          // alert('Gift Packaing Added');
        
//       }
//       });
// }, 1500);
//          });
         
       } else {
         
           $('.custom_product_metas').hide(200);
       }
    });


    
    
