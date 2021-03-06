WooCommerce Custom Product Data Fields
======================================

<img src="https://raw.githubusercontent.com/kharissulistiyo/WooCommerce-Custom-Product-Data-Fields/master/screenshot.png" alt="WooCommerce Custom Product Data Fields"/>

WooCommerce Custom Product Data Fields is a simple framework which will help you to build extra product data fields, e.g. secondary product title, vendor info, custom message for individual product, etc.

You can use this framework as a library of your ‘brand-new’ WooCommerce Extension.

[Download]: http://wordpress.org/plugins/woocommerce-custom-product-data-fields/

[Download][] stable version from WordPress.org plugin repository.


## Installation

1. Upload this plugin to the /wp-content/plugins/ directory.
2. Activate the plugin through the Plugins menu in WordPress.
3. Define your custom product data fields in your theme `functions.php` file. See `fields-init.php` inside this plugin folder.


## Available Fields

At the very first release, supported fields are:

* text
* number
* textarea
* checkbox
* select
* radio
* hidden

## Defining Your Fields

To make your own fields (as seen on the screenshot above), put this example fields in functions.php of your theme.

```
/**
 * (Example) Setting Up The Custom Product Data Fields.
 * Copy this function to your theme functions.php file.
 * Do not rename the function name, otherwise your fields won't be read.
 **/

if(!function_exists('wc_custom_product_data_fields')){

  function wc_custom_product_data_fields(){


    $custom_product_data_fields = array();

    $custom_product_data_fields[] = array(
          'tab_name'    => __('Custom Data', 'wc_cpdf'),
    );

    $custom_product_data_fields[] = array(
          'id'          => '_mytext',
          'type'        => 'text',
          'label'       => __('Text', 'wc_cpdf'),
          'placeholder' => __('A placeholder text goes here.', 'wc_cpdf'),
          'class'       => 'large',
          'description' => __('Field description.', 'wc_cpdf'),
          'desc_tip'    => true,
    );

    $custom_product_data_fields[] = array(
          'id'          => '_mynumber',
          'type'        => 'number',
          'label'       => __('Number', 'wc_cpdf'),
          'placeholder' => __('Number.', 'wc_cpdf'),
          'class'       => 'short',
          'description' => __('Field description.', 'wc_cpdf'),
          'desc_tip'    => true,
    );

    $custom_product_data_fields[] = array(
          'id'          => '_mytextarea',
          'type'        => 'textarea',
          'label'       => __('Textarea', 'wc_cpdf'),
          'placeholder' => __('A placeholder text goes here.', 'wc_cpdf'),
          'style'       => 'width:70%;height:140px;',
          'description' => __('Field description.', 'wc_cpdf'),
          'desc_tip'    => true,
    );

    $custom_product_data_fields[] = array(
          'id'          => '_mycheckbox',
          'type'        => 'checkbox',
          'label'       => __('Checkbox', 'wc_cpdf'),
          'description' => __('Field description.', 'wc_cpdf'),
          'desc_tip'    => true,
    );

    $custom_product_data_fields[] = array(
          'id'          => '_myselect',
          'type'        => 'select',
          'label'       => __('Select', 'wc_cpdf'),
          'options'     => array(
              'option_1'  => 'Option 1',
              'option_2'  => 'Option 2',
              'option_3'  => 'Option 3'
          ),
          'description' => __('Field description.', 'wc_cpdf'),
          'desc_tip'    => true,
    );

    $custom_product_data_fields[] = array(
          'id'          => '_myradio',
          'type'        => 'radio',
          'label'       => __('Radio', 'wc_cpdf'),
          'options'     => array(
                'radio_1' => 'Radio 1',
                'radio_2' => 'Radio 2',
                'radio_3' => 'Radio 3'
          ),
          'description' => __('Field description.', 'wc_cpdf'),
          'desc_tip'    => true,
    );

    $custom_product_data_fields[] = array(
          'id'         => '_myhidden',
          'type'       => 'hidden',
          'value'      => 'Hidden Value',
    );


    return $custom_product_data_fields;


  }



}
```


## Getting The Field Value

```
/**
*
* $wc_cpdf->get_value($post_id, $field_id);
* $post_id = (integer) post ID
* $field_id = (string) unique field ID
*
*/

global $wc_cpdf;

echo $wc_cpdf->get_value(get_the_ID(), '_mytext');
```

## License

[GNU General Public License v3.0]: http://www.gnu.org/licenses/gpl-3.0.html

[GNU General Public License v3.0][]


## More Info

[kharisulistiyo(at)gmail(dot)com]: mailto:kharisulistiyo@gmail.com
[@kharissulistiyo]: http://twitter.com/kharissulistiyo

Contact me:

* Mail: [kharisulistiyo(at)gmail(dot)com][]
* Twitter: [@kharissulistiyo][]
