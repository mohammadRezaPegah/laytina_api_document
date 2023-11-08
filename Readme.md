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

########## Guest url's end ##########



########## Authuenticated url's start ##########

Get user unread notifications
Get profile products
Get profile information
Update profile/logo image
Check user business
Get followers
Get followings
Get business products
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

########## Authuenticated url's end ##########

```

## Guest url's:

### Get exploer stories list

###### url:

```
/stories/get-explor-stories
```

###### method:

** GET **

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
            id: <id>,            content: <image link>
        },
        {
            id: <id>,            content: <image link>
        },
    ]
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

** GET **

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

** GET **

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

** GET **

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

** If length parameter enterd in the request, return's by the lenght else retirn's all the categories **

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

** GET **

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

** The response.page is the next page. exam: you sent 1 and responsed 2 **

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
        page: <number>
        has_more: <boolean>
    ]
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

** POST **

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

###### response items:

```
(number) status
(string) error
(string) path
```

###### response example:

```
Successfuly:
{
    status: 201,
    path: <link>
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

** GET **

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

** GET **

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

** GET **

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

** The response.page is the next page. exam: you sent 1 and responsed 2 **

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
        page: <number>
        has_more: <boolean>
    ]
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

** PATCH **

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

** PATCH **

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

** POST **

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

** POST **

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

** POST **

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

** PATCH **

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

** GET **

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

** GET **

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

** GET **

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

** GET **

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

## Authenticated url's:

### Get user unread notifications

###### url:

```
dashboard/notifications/get-unreaded
```

###### method:

** GET **

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

** GET **

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

** GET **

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

** POST **

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

** GET **

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

** GET **

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

** GET **

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

### Get business products

###### url:

```
dashboard/follow/followings
```

###### method:

** GET **

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

** GET **

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

** POST **

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

** POST **

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

** POST **

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

** POST **

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

** POST **

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

** POST **

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

** GET **

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

** GET **

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <required>
```

###### request entries:

```
(number) page <required>
```

###### notic:

** The response.page is the next page. exam: you sent 1 and responsed 2 **

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
        page: <number>
        has_more: <boolean>
    ]
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

** GET **

###### header:

```
(string) token <required>
(string) username <required>
(string) password <required>
(string) device_token <required>
```

###### request entries:

```
(number) page <required>
```

###### notic:

** The response.page is the next page. exam: you sent 1 and responsed 2 **

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
        page: <number>
        has_more: <boolean>
    ]
}

Error:
{
    status: (206/400/403/404)
    error: <message>
}
```
