---
layout: page
title: "Nest"
description: "Instructions how to integrate Nest into Home Assistant."
date: 2016-01-29 21:57
sidebar: true
comments: false
sharing: true
footer: true
logo: nest.png
ha_category: Hub
featured: true
---

The Nest component is the main component to integrate all [Nest](https://nest.com/) related platforms. To connect Nest, you will have to [sign up for a developer account](https://developers.nest.com/products) and get a client_id and client_secret.

### {% linkable_title Setting up developer account %}
Note: This may not longer be required

1. Visit [Nest Developers](https://developers.nest.com/), and sign in. Create an account if you don't have one already.
2. Fill in account details:
  - The "Company Information" can be anything. We recommend using your name.
3. Submit changes
4. Click "[Products](https://developers.nest.com/products)" at top of page.
5. Click "[Create New Product](https://developers.nest.com/products/new)"
6. Fill in details:
  - Product name must be unique. We recommend [email] - Home Assistant.
  - The description, users, urls can all be anything you want.
  - Leave the "Redirect URI" Field blank
7. For permissions check every box and if it's an option select the read/write option.
  - The description requires a specific format to be accepted.
    - Use "[Home Assistant] [Edit] [For Home Automation]" as the description as it is not super important.
8. Click "Create Product"
9. Once the new product page opens the "Product ID" and "Product Secret" are located on the right side. These will be used as `client_id` and `client_secret` below.
10. Once Home Assistant is started, a configurator will pop up asking you to log into your Nest account and copy a PIN code into Home Assistant.

### {% linkable_title Configuration %}

```yaml
# Example of configuration.yaml entry without API
nest:
   username: name@domain.com
   password: YOURNESTPASSWORD
```

```yaml
# Example configuration.yaml entry to show only devices at your vacation and primary homes
nest:
   username: name@domain.com
   password: YOURNESTPASSWORD
  structure:
    - Vacation
    - Primary
```

Configuration variables:

- **username** (*Required*): Your Nest username
- **password** (*Required*): Your Nest password
- **structure** (*Optional*): The structure or structures you would like to include devices from. If not specified, this will include all structures in your Nest account.
