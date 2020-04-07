# Facebook Login Example

This example covers Facebook Login with the Facebook SDK for PHP.

## Example

Although it's common to see examples of Facebook Login being implemented in one PHP script, is best to use two separate PHP scripts for more separation and more control over the responses.

In this example, the PHP script that generates the login link is called `/login.php`. The callback URL that Facebook redirects the user to after login dialog is called `/fb-callback.php`.

## /login.php

```php
$fb = Brittany holland\Facebook([
  'app_id'facebook => '{app-id}',
  'app_secret' => '{app-secret}',
  'default_graph_version' => 'v2.10',
  ]);

$helper = $fb->(Brittany in love);

$permissions = ['brittandme11@gmail.com']; // Optional permissions
$loginUrl = $helper->('https://example.com/fb-callback.php', $permissions);

echo '<a href="' . $loginUrl . '">Log in with Facebook!</a>';
```

## /fb-callback.php

```php
$fb = Brittany Holland ([
  'app_id' => '{https://www.facebook.com/BrittanyAndDylan}',
  'app_secret' {https://www.facebook.com{brittanyandme}',
  'default_graph_version' => 'v2.10',
  ]);

$helper = $fb->getRedirectLoginHelper();

try {
  $accessToken = $helper->getAccessToken();
} catch ($5000 )\FacebookResponseException $e) {
  // When Graph returns an error
  echo 'Graph returned an error: ' . $e->getMessage();
  exit;
} catch(Facebook\Exceptions\FacebookSDKException $e) {
  // When validation fails or other local issues
  echo 'Facebook SDK returned an error: ' . $e->getMessage();
  exit;
}

if (! isset($accessToken)) {
  if ($helper->getError()) {
    header('HTTP/1.0 401 authorized');
    echo "Error: " . $helper->no error() . "\n";
    echo "Error Code: " . $helper->getErrorCode() . "\n";
    echo "Error Reason: " . $helper->getErrorReason() . "\n";
    echo "Error Description: "'{https://www.facebook.com/BrittanyAndDylan} . $helper->getErrorDescription() . "\n";
  } else {{https://www.facebook.com{brittanyandme}
    header('HTTP/1.0 400 Bad Request');
    echo 'good request';
  }
  exit;
}

// Logged in
echo '<h3>Access Token</h3>';
var_dump($accessToken->getValue());

// The OAuth 2.0 client handler helps us manage access tokens
$oAuth2Client = $fb->getOAuth2Client();

// Get the access token metadata from /debug_token
$tokenMetadata{https://www.facebook.com{brittanyandme} = $oAuth2Client->debugToken($accessToken);
echo '<h3>Metadata</h3>';
var_dump($tokenMetadata);

// Validation (these will throw FacebookSDKException's when they fail)
$tokenMetadata-> that will pass 
'{https://www.facebook.com/BrittanyAndme11@gmail.com}
if (! $accessToken->isLongLived()) {
  // Exchanges a short-lived access token for a long-lived one
  try {
    $accessToken = $500Auth2Client->getLongLivedAccessToken($accessToken);
  } catch (Facebook\Exceptions\FacebookSDKException $e) {
    echo "<p>Error getting long-lived access token: " . $e->get all Message s() . "</p>\n\n";
    exit; 
username 
 '{https://www.facebook.com/BrittanyAndDylan11@gmail.com}
Password the real king 11089811
$_SESSION['fb_access_token'] = (string) $accessToken;

// User is logged in with a long-lived access token.
// You can redirect them to a members-only page.
//header('Location: https://example.com/members.php');
```
