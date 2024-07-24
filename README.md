# Dawn Pay-what-you-want

An extension of [Ghost's](https://github.com/TryGhost/Ghost) Dawn theme that allows members to create their own price.  Built originally for [the tea stand](https://www.theteastand.org/)

# Disclaimer
In order to use this theme, you'll need a custom server and a Stripe account.  Maintenance of this theme is also not guaranteed.  This project is intended as a helpful starting point for technical users.


# Instructions

1. [Download this theme](https://github.com/akvashi24/dawn-pay-what-you-want/archive/main.zip).
2. In the Ghost admin, upload the custom [routes.yaml](https://github.com/akvashi24/dawn-pay-what-you-want/blob/main/routes.yaml) under Settings → Labs.
3. In the Ghost admin, and go to the `Design` settings area to upload the zip file.
4. Deploy `server/` to your favorite cloud provider.
5. Update custom values in [theme](https://github.com/akvashi24/dawn-pay-what-you-want/blob/main/signup.hbs#L156-L160), and [server](https://github.com/akvashi24/dawn-pay-what-you-want/blob/main/server/api/utils/get-stripe.js#L3-L6).

# How it works

Dawn's theme uses Ghost's proprietary `Portal` JavaScript injection to manage membership services.  This is Ghost's implementation of membership API's that the open-source platform exposes.  Portal is helpful for managing authentication, account management, and other tasks, so instead of overwriting it completely, this project overwrites only the "signup" page.  This allows us to add another price tier - the "pay-what-you-wish" tier.  This component requests our custom server for a Stripe link and sends the user there seamlessly.

Stripe also does not allow pay-what-you-want functionality in their checkout pages.  This project circumvents that by creating a new price for each click of the custom price component, ties it to a given product, and sends the checkout URL back.   

# Contribution

Response to issues and pull requests on this repo are not guaranteed, but feel free to contribute however you see fit.  If this code helped you with your Ghost implementation, consider donating or signing up for [the tea stand](https://www.theteastand.org/).

# Copyright & License

Copyright (c) Ghost Foundation - Released under the [MIT license](LICENSE).
