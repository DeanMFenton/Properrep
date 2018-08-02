# Cleeng Sandbox

After tutorial 1 and 2 you should know the basics of our PHP SDK, how to protect content and how to create offers. As you probably have seen there was no option explained yet to test payment process without using real cash.

In this Tutorial, you can learn how to work on our test server Cleeng Sandbox.

Next to be able to experiment around without real money involved, it is wise to use the sandbox to avoid your real reporting (and statistics) are "messed-up" with your test data.
## 1. Introduction

You have to realize that Sandbox works on totally different database, so to start with you have create a separate account:

1. Register a publisher account sandbox registration
2. Get your new Publisher Token from sandbox api-keys

Note: when you switch between servers, think about deleting the cookies in your browser to avoid any conflicts.
## Let's build a sand castle
### 2.1 Creating new offer via Sandbox

As you can see, everything we are doing here is exactly the same but in a different environment. Let's have a look at create_offer.php

To create offers on Sandbox, you have to:

1. Set new publisherToken from Sandbox

` $publisherToken = 'YOUR_SANDBOX_PUBLISHER_TOKEN';`

    which you can find in sandbox api-keys.

     

    Set endpoint to sandbox.

    By default in Api.php you can find:

    protected $endpoint = 'https://api.cleeng.com/3.0/json-rpc'; these are production servers

     
