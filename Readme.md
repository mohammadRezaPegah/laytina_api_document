# Lytina Api

## Requests Name

### Guest url's

##### Start and token genrator

```
App start
```

##### Upload

```
File Upload
```

##### Device localize

```
Set locale
```

##### Home page

```
Get exploer stories list
Get single story
Get selected products by category
Get categories list
Get products by category
```

##### Products page

```
Get products list
```

##### Product show

```
Get product
Get Product tags list
Product mark ** auth user **
```

##### Singin / Register

```
Get roles download file url
Signin with phone
Signin with email
Signin confirmation
```

##### Search

```
Content search
Location search
```

##### business profile to guest user

```
Get Business information
Get Business products
Start following ** auth user **
Business mark ** auth user **
```

##### Location's

```
Get Countries list
Get all states list
Get country states
Get all cities list
Get state cities
```

### Authuenticated url's

###### Sign out

```
Signout
```

##### Notification

```
Get user unread notifications
```

##### Profile

```
Get profile products
Get profile information
Update profile/logo image
Get website management url
```

##### Valid business check management

```
Check user business
```

##### Followers list management

```
Get followers
Unfollow
```

##### Followings list management

```
Get followings
```

##### Marks list(favorite products) management

```
Get user marks
Product unmark
Business unmark
```

##### wallet management

```
Get user wallet credit
```

##### Business products list management

```
Check user business
```

```
Check user has add product access
Get user business products list
Get dashboard business products list
Get product
Get Product tags list
Product create
Product update
Product remove
Product single ladder
Product group ladder store
product group ladder unpaids information
```

##### Business product's group ladder management

```
Get user business products list
Get dashboard business products list
Product group ladder store
product group ladder unpaids information
Check add story access
```

##### Business stories management

```
Get user stories list
Create story
Story renew
Story remove
```

##### Business management

```
Check user business
Get businesses filed list
Get businesses type list
Get licenses list
Get user businesses list
Get user businesses information
Store user business
update user business setting
Get business addresses list
Get business address
Create business address
Update business address
Remove business address
Identity reset start
Identity reset confirm
```

##### Business ladder

```
Business ladder
Business ladder invoice
Business ladder invoice wallet pay
```

##### User invoices

```
User invoices list
```

##### User management

```
Get user information
User update
Reset password start
Reset password confirm
```

##### Subscriptions page

```
Get subscription types list
Get subscription get type
Get subscription type methods
Get subscription method
```

##### Buy subscribtion (invoice)

```
General invoice (any pay method invoice)
Product single ladder invoice
Products group ladder invoice
Business ladder invoice
General invoice wallet pay
Product single ladder invoice wallet pay
Products group ladder invoice wallet pay
```

## Requests Name

```
########## Guest url's start ##########

Get exploer stories list
Get single story
Get selected products by category
Get categories list
Get products by category
File Upload
Get product
Get products list
App start
Set locale
Signin with phone
Signin with email
Signin confirmation
Signout
Location search
Content search
Get Business information
Get Business products
Get Countries list
Get all states list
Get country states
Get all cities list
Get state cities
Get Product tags list
Get roles download file url

########## Guest url's end ##########



########## Authuenticated url's start ##########

Get user unread notifications
Get profile products
Get profile information
Update profile/logo image
Check user business
Get followers
Get followings
Get dashboard business products list
Get user marks
Start following
Unfollow
Product mark
Product unmark
Business mark
Business unmark
Get user wallet credit
Get user business products list
Get user stories list
Get user businesses list
Get user businesses information
Store user business
update user business setting
Get business addresses list
Get business address
Create business address
Update business address
Remove business address
Identity reset start
Identity reset confirm
Create story
Story renew
Story remove
Business ladder
User invoices list
Get user information
User update
Reset password start
Reset password confirm
Check add story access
Get subscription types list
Get subscription get type
Get subscription type methods
Get subscription method
Get website management url
Product create
Product update
Product remove
Product single ladder
Product group ladder store
product group ladder unpaids information
General invoice (any pay method invoice)
Product single ladder invoice
Products group ladder invoice
Business ladder invoice
General invoice wallet pay
Product single ladder invoice wallet pay
Products group ladder invoice wallet pay
Business ladder invoice wallet pay

########## Authuenticated url's end ##########

```

## Guest url's:

### Get exploer stories list

###### url:

```
/story/get-explor-stories
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: {
        "story_id": <number>,
        "user_image": <string>,
        "user_name": <string>,
        "stories": [
            {...},
            {...},
            {...},
        ]
    }
}

Error:
{
    status: (206/403/404)
    error: <string>
}
```

### Get story

###### url:

```
/story/get-story
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(number) story_id <required, numeric>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [ id, type, user, business, slug, phone, email, link, show_time, path, logo, has_next, has_prev, next, prev]
}

Error:
{
    status: (206/403/404)
    error: <string>
}
```

### Story statistic

###### url:

```
/story/statistic
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(number) story_id <required, numeric>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) message
```

###### response example:

```
Successfuly:
{
    status: 200,
    message: <string>
}

Error:
{
    status: (206/403/404)
    error: <string>
}
```

### Get selected products by category

###### url:

```
/products/get-selected-categories
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            id: <id>,
            image: <link>,
            name: <name>,
        },
        {
            id: <id>,
            image: <link>,
            name: <name>,
        },
    ]
}

Error:
{
    status: (206/403/404)
    error: <string>
}
```

### Get Categories list

###### url:

```
/categories/all
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(number) length <nullable, numeric>
```

###### notic:

**If length parameter enterd in the request, return's by the lenght else retirn's all the categories**

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            "id": <id>,
            "name": <name>,
            "slug": <slug>,
            "code": <code>,
            "active": <is active or not(1 or 0)>,
            "image": <link>
        }
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get products by category

###### url:

```
/products/get-by-category
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(number) category_id <required, numeric>
(number) page <required, numeric>
```

###### notic:

**The response.page is the next page. exam: you sent 1 and responsed 2**

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(booloean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            'id' => <id>,
            'name' => <name>,
            'price' => <price, nullable>,
            'person_type' => <business person type>,
            'country' => <country name>,
            'state' => <state/province name>,
            'city' => <city name>,
            'view' => <view length>,
            'created_at' => <created at data (by user local(jalali/gregorian))>,
            'author' => <string>,
            'image' => <image link>
        }
    ],
    page: <number>,
    has_more: <boolean>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### File upload

###### url:

```
/cilivo-file-manager
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(file) file <required, file>
```

###### notic:

**file parameter can be: profile, logo, product, story, certificate, saleExpert and licenses(the parameter name comes from database)**

###### response items:

```
(number) status
(string) error
(string) path
(string) file_name
(string) mime_type
(string) play_time
```

###### response example:

```
Successfuly:
{
    status: 201,
    path: <link>
    file_name: <string>
    mime_type: <string>
    play_time: <string>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### App start

###### url:

```
/app/start
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(string) device <nullable>
(string) ip <nullable>
(string) country <nullable>
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
(string) token
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>
    token : <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Get product

###### url:

```
/products/product
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(number) id <required, numeric>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data : {
        "id": <number>,
        "name": <string>,
        "price": <price, nullable>,
        "person_type": <string>,
        "country": <string>,
        "state": <string>,
        "city": <string>,
        "view": <number>,
        "created_at": <date>,
        "image": <link>,
        "owner_logo": <link>,
        "owner_name": <string>,
        "owner_slug": <string>,
        "description": <text>,
        "phones": [
            {
                "phone": <country_code + phone>,
                "country_code": <string>
            },
            {
                "phone": <country_code + phone>,
                "country_code": <string>
            },
            {
                "phone": <country_code + phone>,
                "country_code": <string>
            },
        ],
        "tags": [
            <string>
            <string>
            <string>
        ]
    }
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Get products list

###### url:

```
/products/list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(number) page <nullable, default: 1>
```

###### notic:

**The response.page is the next page. exam: you sent 1 and responsed 2**

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(booloean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            'id' => <id>,
            'name' => <name>,
            'price' => <price, nullable>,
            'person_type' => <business person type>,
            'country' => <country name>,
            'state' => <state/province name>,
            'city' => <city name>,
            'view' => <view length>,
            'created_at' => <created at data (by user local(jalali/gregorian))>,
            'author' => <string>,
            'image' => <image link>
        }
    ],
    page: <number>,
    has_more: <boolean>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Set locale

###### url:

```
/app/set-locale
```

###### method:

**PATCH**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(string) locale <required>
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 202,
    message: <string>
}

Error:
{
    status: (206/400/403/404/417)
    error: <string>
}
```

### Signin with phone

###### url:

```
/authentication/phone-signin
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <required>
```

###### request entries:

```
(number) phone <required>
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>
}

Error:
{
    status: (206/400/403/404/500/501)
    error: <string>
}
```

### Signin with email

###### url:

```
/authentication/email-signin
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <required>
```

###### request entries:

```
(email) email <required>
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>
}

Error:
{
    status: (206/400/403/404/500/501)
    error: <string>
}
```

### Signin confirmation

###### url:

```
/authentication/confirmation
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <required>
```

###### request entries:

```
(string) code <required>
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
(string) authorization_token
```

###### response example:

```
Successfuly:
{
    status: 201,
    authorization_token: <string>
    message: <string>
}

Error:
{
    status: (206/400/401/403/404/500/501)
    error: <string>
}
```

### Signout

###### url:

```
/authentication/signout
```

###### method:

**PATCH**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 200,
    message: <string>
}

Error:
{
    status: (206/403/404/501)
    error: <string>
}
```

### Location search

###### url:

```
/search/location
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(string) location <required>
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            "country_id": <number, nullable>,
            "country_name": <string, nullable>,
            "state_id": <number, nullable>,
            "state_name": <string, nullable>,
            "city_id": <number, nullable>,
            "city_name": <string, nullable>
        }
    ]
}

Error:
{
    status: (206/403/404)
    error: <string>
}
```

### Content search

###### url:

```
/search/
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(number) page <required>
(string) search <nullable (search query)>
(number) country <nullable (search in country)>
(state) state <nullable (search in state)>
(city) city <nullable (search in city)>
(category) category <nullable (search in category)>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
(number) page (is next page)
(boolean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            "type": <string (Product/Business)>,
            "id": <number>,
            "name": <string>,
            "price": <number, nullable>,
            "person_type": <string>,
            "country": <string>,
            "state": <string>,
            "city": <string>,
            "view": <number>,
            "created_at": <date>,
            "image": <link>
        },
        {
            "type": <string (Product/Business)>,
            "id": <number>,
            "name": <string>,
            "price": <number, nullable>,
            "person_type": <string>,
            "country": <string>,
            "state": <string>,
            "city": <string>,
            "view": <number>,
            "created_at": <date>,
            "image": <link>
        },
    ],
    page: <number>
    has_more: <boolean>
}

Error:
{
    status: (206/403/404)
    error: <string>
}
```

### Get business information

###### url:

```
/business/single
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(string) slug <required>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    "status": 200,
    "data": {
        "id": <number>,
        "user_id": <number>,
        "slug": <string>,
        "logo": <string>,
        "name": <string>,
        "activity_issue": <text>,
        "person_type": <string>,
        "products_len": <number>,
        "followers_len": <number>,
        "followings_len": <number>,
        "followed": <boolean>,
        "website_link": <string>,
        "stories": [
            {
                "user_id": <number>,
                "user_image": <string>,
                "user_name": <string>,
                "stories": [
                    {
                        "story_id": <numeric>,
                        "story_image": <string>,
                        "type": <string>,
                        "user": <string>,
                        "business": <string>,
                        "slug": <string>,
                        "phone": <string>,
                        "email": <string>,
                        "link": <string>,
                        "show_time": <number>,
                        "path": <string>,
                        "logo": <string>
                    },
                    {
                        ...
                    }
                ]
            },
        ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get business products

###### url:

```
/products/business
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(number) page <required>
(number) id <required>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(boolean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        "id": <number>,
        "name": <string>,
        "price": <number, nullable>,
        "person_type": <string>,
        "country": <string>,
        "state": <string>,
        "city": <string>,
        "view": <number>,
        "created_at": <date>,
        "author": <string>,
        "image": <link>
    ],
    "page": <number>,
    "has_more": <boolean>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get countries list

###### url:

```
/location/get-countries
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            name: <string>
            fa_name: <string>
            ar_name: <string>
            en_name: <string>
            nic_name: <string>
            code: <string>
            lang: <string>
        },
        {...},
        {...},
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get all states list

###### url:

```
/location/get-all-states
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            country_id: <number>
            name: <string>
            fa_name: <string>
            ar_name: <string>
            en_name: <string>
            slug: <string>
        },
        {...},
        {...},
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get country states

###### url:

```
/location/get-country-states
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(number) id <requried> (country id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            country_id: <number>
            name: <string>
            fa_name: <string>
            ar_name: <string>
            en_name: <string>
            slug: <string>
        },
        {...},
        {...},
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get all cities list

###### url:

```
/location/get-all-cities
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            state_id: <number>
            name: <string>
            fa_name: <string>
            ar_name: <string>
            en_name: <string>
            slug: <string>
        },
        {...},
        {...},
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get state cities

###### url:

```
/location/get-state-cities
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
(number) id <requried> (state id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            state_id: <number>
            name: <string>
            fa_name: <string>
            ar_name: <string>
            en_name: <string>
            slug: <string>
        },
        {...},
        {...},
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get Product tags list

###### url:

```
/product-tags/list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            id: <number>
            name: <string>
        },
        {...},
        {...},
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get roles download file url

###### url:

```
/download/roles-link
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) link
```

###### response example:

```
Successfuly:
{
    status: 200,
    link: <string>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

## Authenticated url's:

### Get user unread notifications

###### url:

```
/dashboard/notifications/get-unreaded
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            'id' => <number>,
            'send_type' => <string>,
            'title' => <string>,
            'content' => <text>,
            'seen' => <boolean>,
            'seen_at' => <date>,
        },
        {
            'id' => <number>,
            'send_type' => <string>,
            'title' => <string>,
            'content' => <text>,
            'seen' => <boolean>,
            'seen_at' => <date>,
        },
    ]
}

Error:
{
    status: (206/403/404)
    error: <string>
}
```

### Read all notifications

###### url:

```
/dashboard/notifications/read-all
```

###### method:

**PATCH**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    message: <string>
}

Error:
{
    status: (206/403/404)
    error: <string>
}
```

### read single notification

###### url:

```
/dashboard/notifications/read
```

###### method:

**PATCH**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    message: <string>
}

Error:
{
    status: (206/403/404)
    error: <string>
}
```

### Get profile products

###### url:

```
/dashboard/profile/products
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) page <required>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(boolean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            "id": <number>,
            "name": <string>,
            "price": <number, nullable>,
            "person_type": <string>,
            "country": <string>,
            "state": <string>,
            "city": <string>,
            "view": <number>,
            "created_at": <date>,
            "image": <link>
        },
        {
            "id": <number>,
            "name": <string>,
            "price": <number, nullable>,
            "person_type": <string>,
            "country": <string>,
            "state": <string>,
            "city": <string>,
            "view": <number>,
            "created_at": <date>,
            "image": <link>
        },
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get profile information

###### url:

```
/dashboard/profile
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        "id": <number>,
        "name": <string>,
        "products_len": <number>,
        "followers_len": <number>,
        "followings_len": <number>,
        "image": <number>,
        "description": <number>
        "webiste_link" : <link, nullable>
    ]
}

Error:
{
    status: (206/403/404)
    error: <string>
}
```

### Update profile/logo image

###### url:

```
/dashboard/profile/updateProfileImage
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(file) image
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 202,
    path: <link>

}

Error:
{
    status: (206/400/403/406/500)
    error: <string>
}
```

### Check user business

###### url:

```
/dashboard/user/check-business
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    "data": {
        "has_business": <boolean>, // step 1
        "has_confimed_settings": <boolean>, // step 2
        "has_compilite_setting": <boolean> // step 3
    }
}

Error:
{
    status: (206/403/404)
    error: <string>
}
```

### Get followers

###### url:

```
/dashboard/follow/followers
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) page <required>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(boolean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            'is_business' => <boolean>,
            'id' => <number>,
            'business_id' => <number, nullable>,
            'name' => <string>,
            'slug' => <string>,
            'person_type' => <string>,
            'image' => <link>,
            'type' => <string>,
        },
        {
            'is_business' => <boolean>,
            'id' => <number>,
            'business_id' => <number, nullable>,
            'name' => <string>,
            'slug' => <string>,
            'person_type' => <string>,
            'image' => <link>,
            'type' => <string>,
        },
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get followings

###### url:

```
/dashboard/follow/followings
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) page <required>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(boolean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            'is_business' => <boolean>,
            'id' => <number>,
            'business_id' => <number, nullable>,
            'name' => <string>,
            'slug' => <string>,
            'person_type' => <string>,
            'image' => <link>,
            'type' => <string>,
        },
        {
            'is_business' => <boolean>,
            'id' => <number>,
            'business_id' => <number, nullable>,
            'name' => <string>,
            'slug' => <string>,
            'person_type' => <string>,
            'image' => <link>,
            'type' => <string>,
        },
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get dashboard business products list

###### url:

```
/dashboard/business/products/list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) page <required>
(number) id <required> (business_id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(boolean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            "id": <number>,
            "name": <string>,
            "price": <number, nullable>,
            "person_type": <string>,
            "country": <string>,
            "state": <string>,
            "city": <string>,
            "view": <numberstring>,
            "created_at": <date>,
            "author": <string>,
            "image": <link>
        },
        {
            "id": <number>,
            "name": <string>,
            "price": <number, nullable>,
            "person_type": <string>,
            "country": <string>,
            "state": <string>,
            "city": <string>,
            "view": <numberstring>,
            "created_at": <date>,
            "author": <string>,
            "image": <link>
        },
    ]
}

Error:
{
    status: (206/400/401/403)
    error: <string>
}
```

### Get user marks

###### url:

```
/dashboard/mark/marks
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) page <required>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(boolean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [...]
}

Error:
{
    status: (206/400/401/403)
    error: <string>
}
```

### Start following

###### url:

```
/dashboard/follow/follow
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (user_id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>
}

Error:
{
    status: (202/206/400/403/404/500)
    error: <string>
}
```

### Unfollow

###### url:

```
/dashboard/follow/unfollow
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (user_id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 202,
    message: <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Product mark

###### url:

```
/dashboard/mark/product-mark
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (product_id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>
}

Error:
{
    status: (202/206/400/403/404/500)
    error: <string>
}
```

### Product unmark

###### url:

```
/dashboard/mark/product-unmark
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (product_id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 202,
    message: <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Business mark

###### url:

```
/dashboard/mark/business-mark
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (business_id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>
}

Error:
{
    status: (202/206/400/403/404/500)
    error: <string>
}
```

### Business unmark

###### url:

```
/dashboard/mark/business-unmark
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (business_id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 202,
    message: <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Get user wallet credit

###### url:

```
/dashboard/user/wallet-credit
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    'credit': <string>
}

Error:
{
    status: (206/403/404)
    error: <string>
}
```

### Get user business products list

###### url:

```
/dashboard/business/products/list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) page <required>
(number) id <required> (business id)
```

###### notic:

**The response.page is the next page. exam: you sent 1 and responsed 2**

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(booloean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            'id' => <id>,
            'name' => <name>,
            'price' => <price, nullable>,
            'person_type' => <business person type>,
            'country' => <country name>,
            'state' => <state/province name>,
            'city' => <city name>,
            'view' => <view length>,
            'confirmed' => <number(1,0), nullable>
            'created_at' => <created at data (by user local(jalali/gregorian))>,
            'author' => <string>,
            'image' => <image link>
        }
    ],
    page: <number>,
    has_more: <boolean>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get user business products list

###### url:

```
/dashboard/business/products/confirmed
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (business id)
```

###### notic:

**The response.page is the next page. exam: you sent 1 and responsed 2**

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(booloean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            'id' => <id>,
            'name' => <name>,
            'price' => <price, nullable>,
            'person_type' => <business person type>,
            'country' => <country name>,
            'state' => <state/province name>,
            'city' => <city name>,
            'view' => <view length>,
            'confirmed' => <number(1,0), nullable>
            'created_at' => <created at data (by user local(jalali/gregorian))>,
            'author' => <string>,
            'image' => <image link>
        }
    ],
    page: <number>,
    has_more: <boolean>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get user stories list

###### url:

```
/dashboard/stories/list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) page <required>
```

###### notic:

**The response.page is the next page. exam: you sent 1 and responsed 2**

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(booloean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            'id' => <id>,
            'content' => <link>
        }
    ],
    page: <number>,
    has_more: <boolean>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get user businesses list

###### url:

```
/dashboard/business/list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) page <required>
```

###### notic:

**The response.page is the next page. exam: you sent 1 and responsed 2**

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(booloean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            'id' => <id>,
            'name' => <name>,
        }
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get user businesses information

###### url:

```
/dashboard/business/information
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (business id)
```

###### notic:

**The response.page is the next page. exam: you sent 1 and responsed 2**

###### response items:

```
(number) status
(string) error
(array) data
(number) page
(booloean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            'id' => <id>,
            'name' => <name>,
        }
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Store user business

###### url:

```
/dashboard/business/store
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
Real person

(number) person_type <required> (1 is real, 2 is legall)
(number) category <required> (category_id)
(string) field <required>
(string) name <required>
(string) business_name <required>
(string) business_ename <required>
(number) phone <required>
(number) citizen_id <required>
(string) slug <required>
(text) license_issue <required>
(string) business_type <required>
(number) country <required>
(number) state <required>
(number) city <required>


Legall person sum with below parameters

(string) national_id <nullable>
(string) registration_code <nullable>
```

###### notic:

**If user insert national_id, registration_code is nullable else, it is required**

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 201,
    'message': <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### update user business setting

###### url:

```
/dashboard/business/update
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required,number> (business id)
(text) activity_issue <nullable,text>
(email) email <nullable,email>
(number) activity_year <nullable,number>
(string) logo <nullable,string> (uploaded image name)
(string) website <nullable,string>
(string) google_map_link <nullable,string>
```

###### notic:

**Id parameter is the business id**

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 202,
    'message': <string>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get business addresses list

###### url:

```
/dashboard/addresses/list
```

###### method:

**get**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required,number> (business id)
(number) page <required,number>
```

###### notic:

###### response items:

```
(number) status
(string) error
(number) page
(boolean) has_more
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {...},
        {...},
        {...},
    ]
    'page': <number>
    'has_more': <boolean>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get business address

###### url:

```
/dashboard/addresses/address
```

###### method:

**get**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required,number> (address id)
(number) business_id <required,number> (business id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [...]
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Create business address

###### url:

```
/dashboard/addresses/create
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required,number> (business id)
(number) country <required,number> (country id)
(number) state <required,number> (state id)
(number) city <required,number> (city id)
(string) address <required,string>
(array) phones <nullable, array>
```

###### notic:

###### response items:

```
(number) status
(string) message
(string) error
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Update business address

###### url:

```
/dashboard/addresses/update
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required,number> (address id)
(number) business_id <required,number> (business id)
(number) country <required,number> (country id)
(number) state <required,number> (state id)
(number) city <required,number> (city id)
(string) address <required,string>
(array) phones <nullable, array>
```

###### notic:

###### response items:

```
(number) status
(string) message
(string) error
```

###### response example:

```
Successfuly:
{
    status: 202,
    message: <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Remove business address

###### url:

```
/dashboard/addresses/remove
```

###### method:

**DELETE**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required,number> (address id)
(number) business_id <required,number> (business id)
```

###### notic:

###### response items:

```
(number) status
(string) message
(string) error
```

###### response example:

```
Successfuly:
{
    status: 202,
    message: <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Identity reset start

###### url:

```
/dashboard/business/reset-start
```

###### method:

**PUT**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required,number> (business id)
```

###### notic:

###### response items:

```
(number) status
(string) message
(string) error
(number) code_expire
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>
    code_expire: <number>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Identity reset confirme

###### url:

```
/dashboard/business/reset-confirm
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required,number> (business id)
(number) code <required,number> (verification code)
```

###### notic:

###### response items:

```
(number) status
(string) message
(string) error
```

###### response example:

```
Successfuly:
{
    status: 200,
    message: <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Get user stories list

###### url:

```
/dashboard/stories/list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) page <required,number>
```

###### notic:

###### response items:

```
(number) status
(string) message
(string) error
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [...],
    page: <number>
    has_more: <boolean>
}

Error:
{
    status: (206/400/403)
    error: <string>
}
```

### Create story

###### url:

```
/dashboard/stories/create
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(string) filename <required>
(string) mime_type <required>
(any) explore <nullable>
(numeric) play_time <nullable>
```

###### notic:

**play_time on videos is required**

###### response items:

```
(number) status
(string) message
(string) path
(number) id
(string) error
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>,
    path: <link>,
    id: <number>,
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Story renew

###### url:

```
/dashboard/stories/renew
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required>
(any) explore <nullable>
```

###### notic:

###### response items:

```
(number) status
(string) message
(string) error
```

###### response example:

```
Successfuly:
{
    status: 200,
    message: <string>,
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Story remove

###### url:

```
/dashboard/stories/remove
```

###### method:

**Delete**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required>
```

###### notic:

###### response items:

```
(number) status
(string) message
(string) error
```

###### response example:

```
Successfuly:
{
    status: 200,
    message: <string>,
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Business ladder

###### url:

```
/dashboard/business/ladder
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (business id)
```

###### notic:

###### response items:

```
(number) status
(string) message
(string) pay_type (id)
(string) error
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>,
}

Disabled:
    {
        status: 403
        error: <string>
    }
None subscription:

    {
        status: 403
        error: <string>
        pay_type: <number>
    }

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### User invoices list

###### url:

```
/dashboard/user/invoices/list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) page <required>
```

###### notic:

###### response items:

```
(number) status
(array) data
(number) page
(boolean) has_more
(string) error
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            type: <string>
            amount: <string>
            invoice_number: <number>
            tracking_number: <number>
            discount: <string>
            date: <date>
            status: <string>
        },
        {...},
        {...},
    ],
    page: <number>,
    has_more: <boolean>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get user information

###### url:

```
/dashboard/user/information
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(array) data
(string) error
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: {
        'username': <string>,
        'email': <email>,
        'citizen_id': <number>,
        'first_name': <string>,
        'last_name': <string>,
        'image': <link>,
        'phone': <number>,
        'user_referal_code': <string>,
        'confirmed': <boolean>,
        'started_at': <date>
    },
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### User update

###### url:

```
/dashboard/user/update
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(string) first_name <required>
(string) last_name <required>
(string) username <required>
(email) email <required>
(phone) phone <required>
(string) citizen_id <required>
```

###### notic:

###### response items:

```
(number) status
(array) data
(string) error
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: {
        'username': <string>,
        'email': <email>,
        'citizen_id': <number>,
        'first_name': <string>,
        'last_name': <string>,
        'image': <link>,
        'phone': <number>,
        'user_referal_code': <string>,
        'confirmed': <boolean>,
        'started_at': <date>
    },
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Reset password start

###### url:

```
/dashboard/user/password/reset-start
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) message
(string) error
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Reset password confirm

###### url:

```
/dashboard/user/password/reset-confirm
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) code <required> (verification code)
(password) password <required>
(password) password_confirmation <required>
```

###### notic:

###### response items:

```
(number) status
(string) message
(string) error
```

###### response example:

```
Successfuly:
{
    status: 202,
    message: <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Check add story access

###### url:

```
/dashboard/stories/check-add-story-access
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) message
(string) error
```

###### response example:

```
Successfuly:
{
    status: 200,
    can_store: <boolean>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get subscription types list

###### url:

```
/dashboard/saubscriptions/types-all
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {
            "id": <number>,
            "name": <string>,
            "pname": <string>,
            "active": <number>,
            "on_business": <number>
        },
        {...},
        {...},
    ]
}

Error:
{
    status: (206/403)
    error: <string>
}
```

### Get subscription get type

###### url:

```
/dashboard/saubscriptions/type
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (type_id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        "id": <number>,
        "name": <string>,
        "pname": <string>,
        "active": <number>,
        "on_business": <number>
    ]
}

Error:
{
    status: (206/403)
    error: <string>
}
```

### Get subscription type methods

###### url:

```
/dashboard/saubscriptions/type-methods
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (type_id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: [
        {...},
        {...},
        {...}
    ]
}

Error:
{
    status: (206/403)
    error: <string>
}
```

### Get subscription method

###### url:

```
/dashboard/saubscriptions/method
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (method_id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: {
        ...
    }
}

Error:
{
    status: (206/403)
    error: <string>
}
```

### Get website management url

###### url:

```
/dashboard/website/get-management-url
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) link
```

###### response example:

```
Successfuly:
{
    status: 200,
    link: <link>
}

Error:
{
    status: (206/403/500)
    error: <string>
}
```

### Product create

###### url:

```
/dashboard/business/products/create
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (business id)
(number) category <required> (category id)
(string) name <required>
(string) description <required>
(number) price <nullable, numeric>
(string) image <requried> (image name)
(array) tags <nullable>
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
(number) pay_type (pay_type id nullable)
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>
}

Error:
{
    status: (206/401/403/404/500)
    error: <string>
    pay_type: <number, nullable>
}
```

### Product update

###### url:

```
/dashboard/business/products/update
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (product id)
(number) category <required> (category id)
(string) name <required>
(string) description <required>
(number) price <nullable, numeric>
(string) image <nullable> (image name)
(array) tags <nullable>
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>
}

Error:
{
    status: (206/401/403/404/500)
    error: <string>
}
```

### Product remove

###### url:

```
/dashboard/business/products/remove
```

###### method:

**DELETE**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (product id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 200,
    message: <string>
}

Error:
{
    status: (206/401/403/404/500)
    error: <string>
}
```

### Product single ladder

###### url:

```
/dashboard/business/products/ladder
```

###### method:

**PATCH**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (product id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 200,
    message: <string>
}

Error:
{
    status: (206/303/401/403/404/500)
    error: <string>
}
```

### Product group ladder store

###### url:

```
/dashboard/business/products/group-ladder
```

###### method:

**PATCH**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(array) ids <required> (product ids list)
(number) business_id <required> (business id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: 201,
    message: <string>
}

Error:
{
    status: (206/401/403/404/500)
    error: <string>
}
```

### product group ladder unpaids information

###### url:

```
/dashboard/terial/get-group-ladder-unpaid-information
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(string) message
```

###### response example:

```
Successfuly:
{
    status: (200, 201),
    message: <string>,
    data: {
        'ladder_cost': <nyumber>,
        'amount': <number>,
        'paid_len': <number>,
        'unpaid_len': <number>,
        'ladders_len': <number>,
        'pay_method': <number> (id),
        'can_pay_with_wallet': <boolean>
    }
}

Error:
{
    status: (206/401/403/404/500)
    error: <string>
}
```

### General invoice

###### url:

```
/dashboard/user/invoices/general
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) method <required> (pay method id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    "status": 200,
    "data": {
        "calculated_price": {
            "amount": <number>,
            "refer_discount": <number>,
            "festival": <number>,
            "discount_amount": <number>,
            "tax": <number>,
            "final": <number>,
            "t_f": <number>
        },
        "amount": <number>,
        "tax": <number>,
        "festival": <number>,
        "discount_amount": <number>,
        "refer_discount": <number>,
        "method_amount": <number>,
        "precent": <number>,
        "ref_dis": <number>,
        "can_pay_with_wallet" => <boolean>,
        "wallet_credit" => <number>,
        "description" => <string>,
        'pay_paths' => {
            'wallet' => {
                "method_type" => "GET",
                'path' => <string>,
                'parameters' => {
                    "invoice" => <number>,
                    'method' => <number>,
                }
            },
            'zarinpal' => {
                "method_type" => "GET",
                'path' => <string, nullable>,
                'parameters' => {
                    'method' => <number>,
                },
            },
            'payping' => {
                "method_type" => "GET",
                'path' => <string, nullable>,
                'parameters' => {
                    'method' => <number>,
                },
            },
        },
    }
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Wallet add credit invoice

###### url:

```
/dashboard/user/invoices/wallet-add-credit
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) amount <required, numeric> // Toomans
(string) discount_code <nullable>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    "status": 200,
    "data": {
        "payable": <number>,
        "amount": <string>,
        "tax": <number>,
        "festival": <number>,
        "discount_amount": <number>,
        "refer_discount": <number>,
        "method_amount": <string>,
        "precent": <number>,
        "ref_dis": <number>,
        "can_pay_with_wallet": <boolean>,
        "description": <string>,
        "pay_paths": {
            "zarinpal": {
                "route_method": <string>,
                "path": <string>,
                "parameters": {
                    "gateway": <string>,
                    "invoice": <number>,
                    "user": number,
                    "discount_code": <string, nullable>,
                    "is_app": <string>,
                    "is_test": <boolean>
                }
            },
            "payping": {
                "route_method": <string>,
                "path": <string>,
                "parameters": {
                    "gateway": <string>,
                    "invoice": <number>,
                    "user": number,
                    "discount_code": <string, nullable>,
                    "is_app": <string>,
                    "is_test": <boolean>
                }
            }
        }
    }
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Product single ladder invoice

###### url:

```
/dashboard/user/invoices/product-single-ladder
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required> (product id)
(number) business_id <required> (business id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    "status": 200,
    "data": {
        "calculated_price": {
            "amount": <number>,
            "refer_discount": <number>,
            "festival": <number>,
            "discount_amount": <number>,
            "tax": <number>,
            "final": <number>,
            "t_f": <number>
        },
        "amount": <number>,
        "tax": <number>,
        "festival": <number>,
        "discount_amount": <number>,
        "refer_discount": <number>,
        "method_amount": <number>,
        "precent": <number>,
        "ref_dis": <number>,
        "can_pay_with_wallet" => <boolean>,
        "wallet_credit" => <number>,
        "description" => <string>,
        "pay_paths" => {
            "wallet" => {
                "method_type" => "GET",
                "path" => <string>,
                "parameters" => {
                    "invoice" => <number>,
                    "id" => <number, product id>,
                    "business_id" => <number, business id>,
                }
            },
            "zarinpal" => {
                "method_type" => "GET",
                "path" => <string, nullable>,
                "parameters" => {
                    "invoice" => <number>,
                    "id" => <number, product id>,
                    "business_id" => <number, business id>,
                },
            },
            "payping" => {
                "method_type" => "GET",
                "path" => <string, nullable>,
                "parameters" => {
                    "invoice" => <number>,
                    "id" => <number, product id>,
                    "business_id" => <number, business id>,
                },
            },
        },
    }
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Products group ladder invoice

###### url:

```
/dashboard/user/invoices/products-group-ladder
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    "status": 200,
    "data": {
       "amount_per_ladder": <number>,
        "tax_per_ladder": <number>,
        "payable": <number>,
        "amount": <number>,
        "tax": <number>,
        "festival": <number>,
        "discount_amount": <number>,
        "refer_discount": <number>,
        "method_amount": <number>,
        "precent": <number>,
        "ref_dis": <number>,
        "can_pay_with_wallet": <boolean>,
        "wallet_credit": <number>,
        "description": <string>,
        "lenght": <number>,
        "pay_paths" => {
            "wallet" => {
                "method_type" => "GET",
                "path" => <string>,
                "parameters" => {
                    "invoice" => <number>,
                }
            },
            "zarinpal" => {
                "method_type" => "GET",
                "path" => <string, nullable>,
                "parameters" => {
                    "invoice" => <number>,
                },
            },
            "payping" => {
                "method_type" => "GET",
                "path" => <string, nullable>,
                "parameters" => {
                    "invoice" => <number>,
                },
            },
        },
    }
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Business ladder invoice

###### url:

```
/dashboard/user/invoices/business-ladder
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    "status": 200,
    "data": {
        "calculated_price": {
            "amount": <number>,
            "refer_discount": <number>,
            "festival": <number>,
            "discount_amount": <number>,
            "tax": <number>,
            "final": <number>,
            "sum_tax_final": <number>
        },
        "payable": <number>,
        "amount": <number>,
        "tax": <number>,
        "festival": <number>,
        "discount_amount": <number>,
        "refer_discount": <number>,
        "method_amount": <number>,
        "precent": <number>,
        "ref_dis": <number>,
        "can_pay_with_wallet": <boolean>,
        "wallet_credit": <number>,
        "description": <string>,
        "pay_paths" => {
            "wallet" => {
                "method_type" => "GET",
                "path" => <string>,
                "parameters" => {
                    "invoice" => <number>,
                    "id" => <number>
                }
            },
            "zarinpal" => {
                "method_type" => "GET",
                "path" => <string, nullable>,
                "parameters" => {
                    "invoice" => <number>,
                    "id" => <number>
                },
            },
            "payping" => {
                "method_type" => "GET",
                "path" => <string, nullable>,
                "parameters" => {
                    "invoice" => <number>,
                    "id" => <number>
                },
            },
        },
    }
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### General invoice wallet pay

###### url:

```
/dashboard/user/invoices/pay/wallet/general
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) invoice <required> (invoice_id)
(number) method <requried> (method id)
(number) business_id <nullable> (business id)
(string) discount_code <nullable>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    "status": 202,
    "message": [
        <string>,
        <string>
    ]
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Product single ladder invoice wallet pay

###### url:

```
/dashboard/user/invoices/pay/wallet/single-ladder
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) invoice <required> (invoice_id)
(number) id <requried> (product id)
(number) business_id <required> (business id)
(string) discount_code <nullable>
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    "status": 202,
    "message": <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Products group ladder invoice wallet pay

###### url:

```
/dashboard/user/invoices/pay/wallet/group-ladder
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) invoice <required> (invoice_id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    "status": 202,
    "message": <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Business ladder invoice wallet pay

###### url:

```
/dashboard/user/invoices/pay/wallet/business-ladder
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
(number) invoice <required> (invoice_id)
(number) id <required> (business_id)
```

###### notic:

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    "status": 202,
    "message": <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <string>
}
```

### Get businesses filed list

###### url:

```
/dashboard/business/field-list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

**The response.page is the next page. exam: you sent 1 and responsed 2**

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: {
        <string>,
        <string>,
        <string>,
        <string>,
        <string>,
        <string>,
    }
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get businesses type list

###### url:

```
/dashboard/business/type-list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

**The response.page is the next page. exam: you sent 1 and responsed 2**

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: {
        {
            id: <number>,
            name: <string>,
            pname: <string>,
            person_type: <string> // real person or legall person,
            knowledge: <boolean>,
        },
    }
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Get licenses list

###### url:

```
/dashboard/business/license-list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

**The response.page is the next page. exam: you sent 1 and responsed 2**

###### response items:

```
(number) status
(string) error
(array) data
```

###### response example:

```
Successfuly:
{
    status: 200,
    data: {
        {
            "id": <number>,
            "name": <string>,
            "pname": <string>,
            "nic_name": <string>, // On upload use this key for parameter name
            "type": <string>,
            "person_type": <string>,
            "is_required": <number> (0 or 1)
        },
    }
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```

### Check user has add product access

###### url:

```
/dashboard/business/products/add-product-access
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <nullable>
(string) authorization_token <required>
```

###### request entries:

```
none
```

###### notic:

**The response.page is the next page. exam: you sent 1 and responsed 2**

###### response items:

```
(number) status
(string) error
(boolean) has_access
```

###### response example:

```
Successfuly:
{
    status: 200,
    has_access: <boolean>
}

Error:
{
    status: (206/400/403/404)
    error: <string>
}
```
