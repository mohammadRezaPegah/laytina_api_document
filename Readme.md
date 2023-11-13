# Lytina Api

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

########## Authuenticated url's end ##########

```

## Guest url's:

### Get exploer stories list

###### url:

```
/stories/get-explor-stories
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
    error: <message>
}
```

### Get story

###### url:

```
/stories/get-story
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
}
```

### File upload

###### url:

```
/file/upload
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
    error: <message>
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
    message: <message>
    token : <string>
}

Error:
{
    status: (206/400/403/404/500)
    error: <message>
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
    error: <message>
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
    error: <message>
}
```

### App start

###### url:

```
/app/start
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
    tokenmessage: <string>
}

Error:
{
    status: (206/403/500)
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    status: 200,
    data: [
       "id": <number>,
       "user_id": <number>,
        "slug": <string>,
        "logo": <link>,
        "name": <string>,
        "activity_issue": <text>,
        "person_type": <string>,
        "product_len": <number>,
        "followers_len": <number>,
        "followings_len": <number>
    ],
}

Error:
{
    status: (206/400/403/404)
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
}
```

## Authenticated url's:

### Get user unread notifications

###### url:

```
dashboard/notifications/get-unreaded
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    error: <message>
}
```

### Get profile products

###### url:

```
dashboard/profile/products
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    error: <message>
}
```

### Get profile information

###### url:

```
dashboard/profile
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    error: <message>
}
```

### Update profile/logo image

###### url:

```
dashboard/profile/updateProfileImage
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    error: <message>
}
```

### Check user business

###### url:

```
dashboard/user/check-business
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    error: <message>
}
```

### Get followers

###### url:

```
dashboard/follow/followers
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
            'name' => <string>,
            'slug' => <string>,
            'person_type' => <string>,
            'image' => <link>,
            'type' => <string>,
        },
        {
            'is_business' => <boolean>,
            'id' => <number>,
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
    error: <message>
}
```

### Get followings

###### url:

```
dashboard/follow/followings
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
            'name' => <string>,
            'slug' => <string>,
            'person_type' => <string>,
            'image' => <link>,
            'type' => <string>,
        },
        {
            'is_business' => <boolean>,
            'id' => <number>,
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
    error: <message>
}
```

### Get dashboard business products list

###### url:

```
dashboard/business/products/list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    error: <message>
}
```

### Get user marks

###### url:

```
dashboard/mark/marks
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    error: <message>
}
```

### Start following

###### url:

```
dashboard/follow/follow
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    message: <message>
}

Error:
{
    status: (202/206/400/403/404/500)
    error: <message>
}
```

### Unfollow

###### url:

```
dashboard/follow/unfollow
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    message: <message>
}

Error:
{
    status: (206/400/403/404/500)
    error: <message>
}
```

### Product mark

###### url:

```
dashboard/mark/product-mark
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    message: <message>
}

Error:
{
    status: (202/206/400/403/404/500)
    error: <message>
}
```

### Product unmark

###### url:

```
dashboard/mark/product-unmark
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    message: <message>
}

Error:
{
    status: (206/400/403/404/500)
    error: <message>
}
```

### Business mark

###### url:

```
dashboard/mark/business-mark
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    message: <message>
}

Error:
{
    status: (202/206/400/403/404/500)
    error: <message>
}
```

### Business unmark

###### url:

```
dashboard/mark/business-unmark
```

###### method:

**POST**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    message: <message>
}

Error:
{
    status: (206/400/403/404/500)
    error: <message>
}
```

### Get user wallet credit

###### url:

```
dashboard/user/wallet-credit
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    error: <message>
}
```

### Get user business products list

###### url:

```
/dashboard/business/products
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required,number> (address id)
(number) business_id <required,number> (business id)
(number) page <required,number>
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
    error: <message>
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
(string) authorization_token <required>
```

###### request entries:

```
(number) id <required,number> (business id)
(number) country <required,number> (country id)
(number) state <required,number> (state id)
(number) city <required,number> (city id)
(string) address <required,string>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
        error: <message>
    }
None subscription:

    {
        status: 403
        error: <message>
        pay_type: <number>
    }

Error:
{
    status: (206/400/403/404/500)
    error: <message>
}
```

### User invoices list

###### url:

```
/dashboard/user/incoives/list
```

###### method:

**GET**

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
}
```

### Get subscription get type

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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    error: <message>
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
    status: (206/401/403/404)
    error: <message>
}
```
