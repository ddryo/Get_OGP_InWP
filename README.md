# Get_OGP_InWP
Get OGP information of external site by utilizing WordPress function


# Usage

```
require_once 'get_ogp_inwp.php';

$url = 'https://example.com/hoge/';

$ogps = \Get_OGP_InWP::get( $url );
```

## About the second argument
You can specify arguments to pass to wp_remote_get().


```
require_once 'get_ogp_inwp.php';

$url = 'https://example.com/hoge/';

// For example like this. (This is the default value)
$fetch_args = [
	'timeout'     => 15,
	'redirection' => 3,
	'sslverify'   => false,
];

$ogps = \Get_OGP_InWP::get( $url, $fetch_args );
```

## About the 3rd argument
You can specify the OGP and metadata you want to acquire


```
require_once 'get_ogp_inwp.php';

$url = 'https://example.com/hoge/';

// For example like this. (This is the default value)
$targets = [
	'title'    => true,
  'icon'     => true,
  'og'       => true,
  'fb'       => true,
  'twitter'  => true,
  'meta'     => [
    'description',
    'thumbnail',
  ],
];

$ogps = \Get_OGP_InWP::get( $url, null, $targets );
```
