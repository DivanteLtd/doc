Earning Rule
============

These endpoints will allow you to easily manage Earning Rules.



Get a complete list of earning rules
------------------------------------

To retrieve a paginated list of earning rules, you need to call the ``/api/<storeCode>/earningRule`` endpoint with the ``GET`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    GET  /api/<storeCode>/earningRule

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| <storeCode>                         | query          | Code of the store to get the earning rules of.    |
+-------------------------------------+----------------+---------------------------------------------------+
| active                              | query          | *(optional)* Possible values: active, inactive    |
+-------------------------------------+----------------+---------------------------------------------------+
| page                                | query          | *(optional)* Start from page, by default 1        |
+-------------------------------------+----------------+---------------------------------------------------+
| perPage                             | query          | *(optional)* Number of items to display per page, |
|                                     |                | by default = 10                                   |
+-------------------------------------+----------------+---------------------------------------------------+
| sort                                | query          | *(optional)* Sort by column name                  |
+-------------------------------------+----------------+---------------------------------------------------+
| direction                           | query          | *(optional)* Direction of sorting [ASC, DESC],    |
|                                     |                | by default = ASC                                  |
+-------------------------------------+----------------+---------------------------------------------------+

To see the first page of all earning rules, use the method below:

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/earningRule \
        -X "GET" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "earningRules": [
        {
          "levels": [
            "000096cf-32a3-43bd-9034-4df343e5fd93"
          ],
          "segments": [],
          "earningRuleId": "00000000-0000-474c-b092-b0dd880c0121",
          "name": "Facebook like test rule",
          "description": "sth",
          "active": true,
          "startAt": "2018-01-19T09:45:00+0100",
          "endAt": "2018-03-19T09:45:00+0100",
          "allTimeActive": false,
          "usages": [],
          "eventName": "facebook_like",
          "pointsAmount": 100,
          "limit": {},
          "type": "custom_event",
          "hasPhoto": false,
          "usageUrl": "http://backend.openloyalty.test.openloyalty.io/api/v1/earnRule/facebook_like/customer/:customerId",
          "segmentNames": [],
          "levelNames": {
            "000096cf-32a3-43bd-9034-4df343e5fd93": "level0"
          }
        },
        {
          "levels": [
            "000096cf-32a3-43bd-9034-4df343e5fd93"
          ],
          "segments": [],
          "earningRuleId": "7664138c-b5a4-4dcd-80ba-0049a92166db",
          "name": "name",
          "description": "description",
          "active": true,
          "allTimeActive": true,
          "usages": [],
          "eventName": "custom_event_name",
          "pointsAmount": 1,
          "limit": {
            "active": false
          },
          "type": "custom_event",
          "hasPhoto": false,
          "usageUrl": "http://backend.openloyalty.test.openloyalty.io/api/v1/earnRule/custom_event_name/customer/:customerId",
          "segmentNames": [],
          "levelNames": {
            "000096cf-32a3-43bd-9034-4df343e5fd93": "level0"
          }
        }
      ],
      "total": 2
    }


Get earning rule details
------------------------

To retrieve a specific earning rule's details, you need to call the ``/api/<storeCode>/earningRule/<earningRule>`` endpoint with the ``GET`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    GET  /api/<storeCode>/earningRule/<earningRule>

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| <storeCode>                         | query          | Code of the store to get the earning rule from.   |
+-------------------------------------+----------------+---------------------------------------------------+
| <earningRule>                       | query          | earningRule ID                                    |
+-------------------------------------+----------------+---------------------------------------------------+

Example
^^^^^^^

 To see details of the earning rule with id ``earningRule = 00000000-0000-474c-b092-b0dd880c0121``, use the method below:

.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/earningRule/00000000-0000-474c-b092-b0dd880c0121 \
        -X "GET" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.

.. note::

    The *earningRule = 00000000-0000-474c-b092-b0dd880c0121* id is an example value. Your value may be different.
    Check the list of all earning rules if you are not sure which id should be used.

Example Response
^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "levels": [
        "000096cf-32a3-43bd-9034-4df343e5fd93"
      ],
      "segments": [],
      "earningRuleId": "00000000-0000-474c-b092-b0dd880c0121",
      "name": "Facebook like test rule",
      "description": "sth",
      "active": true,
      "startAt": "2018-01-19T09:45:00+0100",
      "endAt": "2018-03-19T09:45:00+0100",
      "allTimeActive": false,
      "usages": [],
      "eventName": "facebook_like",
      "pointsAmount": 100,
      "limit": {},
      "type": "custom_event",
      "hasPhoto": false,
      "usageUrl": "http://backend.openloyalty.test.openloyalty.io/api/v1/earnRule/facebook_like/customer/:customerId",
      "segmentNames": [],
      "levelNames": {
        "000096cf-32a3-43bd-9034-4df343e5fd93": "level0"
      }
    }



Get earning rule details (seller)
---------------------------------

To retrieve a page of earning rule details, you need to call the ``/api/<storeCode>/seller/earningRule/<earningRule>`` endpoint with the ``GET`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    GET  /api/<storeCode>/seller/earningRule/<earningRule>

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| <storeCode>                         | query          | Code of the store to get the earning rule from.   |
+-------------------------------------+----------------+---------------------------------------------------+
| <earningRule>                       | query          | earningRule ID                                    |
+-------------------------------------+----------------+---------------------------------------------------+

Example
^^^^^^^

 To see the earning rule with id ``earningRule = 00000000-0000-474c-b092-b0dd880c0725``, use the method below:

.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/seller/earningRule/00000000-0000-474c-b092-b0dd880c0725 \
        -X "GET" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.

.. note::

    The *earningRule = 00000000-0000-474c-b092-b0dd880c0725* id is an example value. Your value may be different.
    Check the list of all earning rules if you are not sure which id should be used.

Example Response
^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "levels": [
        "000096cf-32a3-43bd-9034-4df343e5fd93"
      ],
      "segments": [],
      "earningRuleId": "00000000-0000-474c-b092-b0dd880c0725",
      "name": "Newsletter subscription test rule",
      "description": "sth",
      "active": false,
      "startAt": "2018-01-19T09:45:00+0100",
      "endAt": "2018-03-19T09:45:00+0100",
      "allTimeActive": false,
      "usages": [],
      "eventName": "oloy.customer.newsletter_subscription",
      "pointsAmount": 85,
      "type": "event",
      "hasPhoto": false,
      "segmentNames": [],
      "levelNames": {
        "000096cf-32a3-43bd-9034-4df343e5fd93": "level0"
      }
    }


Create a new earning rule
-------------------------

To create a new earning rule, you need to call the ``/api/<storeCode>/earningRule`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/<storeCode>/earningRule

+----------------------------------+----------------+--------------------------------------------------------------------------+
| Parameter                        | Parameter type | Description                                                              |
+==================================+================+==========================================================================+
| Authorization                    | header         | Token received during authentication                                     |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| <storeCode>                      | query          | Code of the store to create the earning rule in.                         |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[type]                | request        | The type of earning points. Possible types: Custom event rule, Customer  |
|                                  |                | Referral, Event Rule, General spending rule, Multiple earned points,     |
|                                  |                | Product Purchase, Multiple by product labels                             |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[rewardType]          | request        | Who will be rewarded. Possible types:                                    |
|                                  |                | referred,referrer, both                                                  |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[name]                | request        | EarningRule name                                                         |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[description]         | request        | A short description                                                      |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[endAt]               | request        | earningRule visible to YYYY-MM-DD HH:mm, e.g.: ``2019-10-05 10:59``.     |
|                                  |                | *(required only if ``allTimeActive=0``)*                                 |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[startAt]             | request        | earningRule visible from YYYY-MM-DD HH:mm, e.g.: ``2017-10-05 10:59``.   |
|                                  |                | *(required only if ``allTimeActive=0``)*                                 |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[active]              | request        | Set 1 if active, otherwise 0                                             |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[pointsAmount]        | request        | How many points customer can earn                                        |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[target]              | request        | Set ``level`` to choose target from defined levels.                      |
|                                  |                | Set ``segment`` to choose target from defined segments                   |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[levels]              | request        | Array of level IDs. *(required only if ``target=level``)*                |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[segments]            | request        | Array of segment IDs. *(required only if ``target=segment``)*            |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[limit][active]       | request        | Set 1 if usage limit active, otherwise 0                                 |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[limit][period]       | request        | Period usage limit. *(required only if ``[limit][active]=1``)*           |
|                                  |                | Possible parameters: day,week,month,3months,6months,year,forever         |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[limit][limit]        | request        | Usage limit. *(required only if ``[limit][active]=1``)*                  |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[eventName]           | request        | Custom Event name                                                        |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[allTimeActive]       | request        | Set 1 if always visible, otherwise 0                                     |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[excludeDeliveryCost] | request        | Points will not be calculated for delivery cost. Set 1 to active,        |
|                                  |                | otherwise 0                                                              |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[excludedSKUs]        | request        | Excluding products with the given SKU                                    |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[minOrderValue]       | request        | Points will not be calculated for whole purchase if its value will be    |
|                                  |                | below value                                                              |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[inclusionType]       | request        | Accepted values: [include_labels, exclude_labels]. If include_labels is  |
|                                  |                | set - includedLabels will be used.                                       |
|                                  |                | if exclude_labels is set - excludedLabels will be used.                  |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[excludedLabels]      | request        | Points will not be calculated for the purchase of products with defined  |
|                                  |                | labels                                                                   |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[includedLabels]      | request        | Points will be calculated only for the purchase of products with defined |
|                                  |                | labels                                                                   |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[multiplier]          | request        | Points gained for product purchase will be multiplied by this factor     |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[labelMultipliers]    | request        | Points gained for product purchase by labels will be multiplied          |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[skuIds][0]           | request        | Refers to products with the given SKU                                    |
+----------------------------------+----------------+--------------------------------------------------------------------------+

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/earningRule \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "earningRule[active]=1" \
        -d "earningRule[type]=event" \
        -d "earningRule[description]=test" \
        -d "earningRule[endAt]=2018-03-19+09:45" \
        -d "earningRule[eventName]=oloy.customer.logged_in" \
        -d "earningRule[levels][0]=000096cf-32a3-43bd-9034-4df343e5fd93" \
        -d "earningRule[name]=nowy+rule" \
        -d "earningRule[pointsAmount]=5" \
        -d "earningRule[segments]=[+]" \
        -d "earningRule[startAt]=2019-03-19+09:45" \
        -d "earningRule[target]=level" \
        -d "earningRule[limit][active]=1" \
        -d "earningRule[limit][period]=month" \
        -d "earningRule[limit][limit]=5" \
        -d "earningRule[rewardType]=both" \
        -d "earningRule[allTimeActive]=0" \
        -d "earningRule[excludeDeliveryCost]=true" \
        -d "earningRule[excludedSKUs]=123" \
        -d "earningRule[minOrderValue]=2" \
        -d "earningRule[inclusionType]=exclude_labels" \
        -d "earningRule[excludedLabels]=1:1" \
        -d "earningRule[multiplier]=2" \
        -d "earningRule[skuIds][0]=SKU123"

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.

.. note::

    The *000096cf-32a3-43bd-9034-4df343e5fd93* or *00000000-0000-474c-b092-b0dd880c0121* id are example values.
    Your value may be different. Check the list of all levels if you are not sure which id should be used.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json
    {
      "earningRuleId": "3e3d8a3a-2efb-4283-87c4-20b286bde19c"
    }



Edit an existing earning rule
-----------------------------

To edit an existing earning rule, you need to call the ``/api/<storeCode>/earningRule/<earningRule>`` endpoint with the ``PUT`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    PUT  /api/<storeCode>/earningRule/<earningRule>

+----------------------------------+----------------+--------------------------------------------------------------------------+
| Parameter                        | Parameter type | Description                                                              |
+==================================+================+==========================================================================+
| Authorization                    | header         | Token received during authentication                                     |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| <storeCode>                      | query          | Code of the store the updated earning rule belongs to.                   |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| <earningRule>                    | query          | EarningRule ID                                                           |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[type]                | request        | The type of earning points. Possible types: Custom event rule, Customer  |
|                                  |                | Referral, Event Rule, General spending rule, Multiple earned points,     |
|                                  |                | Product Purchase, Multiple by product labels                             |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[rewardType]          | request        | Who will be rewarded. Possible types:                                    |
|                                  |                | referred,referrer, both                                                  |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[name]                | request        | Earning Rule name                                                        |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[description]         | request        | A short description                                                      |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[endAt]               | request        | earningRule visible to YYYY-MM-DD HH:mm, e.g.: ``2019-10-05 10:59``.     |
|                                  |                | *(required only if ``allTimeActive=0``)*                                 |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[startAt]             | request        | earningRule visible from YYYY-MM-DD HH:mm, e.g.: ``2017-10-05 10:59``.   |
|                                  |                | *(required only if ``allTimeActive=0``)*                                 |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[active]              | request        | Set 1 if active, otherwise 0                                             |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[pointsAmount]        | request        | How many points customer can earn                                        |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[target]              | request        | Set ``level`` to choose target from defined levels.                      |
|                                  |                | Set ``segment`` to choose target from defined segments                   |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[levels]              | request        | Array of level IDs. *(required only if ``target=level``)*                |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[segments]            | request        | Array of segment IDs. *(required only if ``target=segment``)*            |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[limit][active]       | request        | Set 1 if usage limit active, otherwise 0                                 |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[limit][period]       | request        | Period usage limit. *(required only if ``[limit][active]=1``)*           |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[limit][limit]        | request        | Usage limit. *(required only if ``[limit][active]=1``)*                  |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[eventName]           | request        | Custom Event name                                                        |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[allTimeActive]       | request        | Set 1 if always visible, otherwise 0                                     |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[excludeDeliveryCost] | request        | Points will not be calculated for delivery cost. Set 1 to active,        |
|                                  |                | otherwise 0                                                              |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[excludedSKUs]        | request        | Excluding products with the given SKU                                    |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[minOrderValue]       | request        | Points will not be calculated for whole purchase if its value will be    |
|                                  |                | below value                                                              |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[inclusionType]       | request        | Accepted values: [include_labels, exclude_labels]. If include_labels is  |
|                                  |                | set - includedLabels will be used.                                       |
|                                  |                | if exclude_labels is set - excludedLabels will be used.                  |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[excludedLabels]      | request        | Points will not be calculated for the purchase of products with defined  |
|                                  |                | labels                                                                   |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[includedLabels]      | request        | Points will be calculated only for the purchase of products with defined |
|                                  |                | labels                                                                   |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[multiplier]          | request        | Points gained for product purchase will be multiplied by this factor     |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[labelMultipliers]    | request        | Points gained for product purchase by labels will be multiplied          |
+----------------------------------+----------------+--------------------------------------------------------------------------+
| earningRule[skuIds][0]           | request        | Refers to products with the given SKU                                    |
+----------------------------------+----------------+--------------------------------------------------------------------------+

Example
^^^^^^^

To fully update an earning rule with id ``earningRule = 00000000-0000-474c-b092-b0dd880c0121``, use the method below:

.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/earningRule/00000000-0000-474c-b092-b0dd880c0121 \
        -X "PUT" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "earningRule[active]=1" \
        -d "earningRule[type]=event" \
        -d "earningRule[description]=something" \
        -d "earningRule[endAt]=2018-03-19+09:45" \
        -d "earningRule[eventName]=facebook_like" \
        -d "earningRule[levels][0]=000096cf-32a3-43bd-9034-4df343e5fd93" \
        -d "earningRule[name]=Facebook+like+test+rule" \
        -d "earningRule[pointsAmount]=9" \
        -d "earningRule[segments]=[+]" \
        -d "earningRule[startAt]=2019-03-19+09:45" \
        -d "earningRule[target]=level" \
        -d "earningRule[limit][active]=1" \
        -d "earningRule[limit][period]=month" \
        -d "earningRule[limit][limit]=5" \
        -d "earningRule[rewardType]=both" \
        -d "earningRule[allTimeActive]=0" \
        -d "earningRule[excludeDeliveryCost]=true" \
        -d "earningRule[excludedSKUs]=123" \
        -d "earningRule[minOrderValue]=2" \
        -d "earningRule[inclusionType]=exlude_labels" \
        -d "earningRule[excludedLabels]=1:1" \
        -d "earningRule[multiplier]=2" \
        -d "earningRule[skuIds][0]=SKU123"


.. warning::

    Remember, you must update the all data of the earningRule.

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.

.. note::

    The *000096cf-32a3-43bd-9034-4df343e5fd93* or *00000000-0000-474c-b092-b0dd880c0121* id are example values.
    Your value may be different. Check the list of all levels if you are not sure which id should be used.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "earningRuleId": "00000000-0000-474c-b092-b0dd880c0121"
    }



Change earning rule status
--------------------------

To make an earning rule active or inactive, you need to call the ``/api/<storeCode>/earningRule/<earningRule>/activate`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST  /api/<storeCode>/earningRule/<earningRule>/activate

+---------------+----------------+--------------------------------------------------------+
| Parameter     | Parameter type | Description                                            |
+===============+================+========================================================+
| Authorization | header         | Token received during authentication                   |
+---------------+----------------+--------------------------------------------------------+
| <storeCode>   | query          | Code of the store the updated earning rule belongs to. |
+---------------+----------------+--------------------------------------------------------+
| <earningRule> | query          | earningRule ID                                         |
+---------------+----------------+--------------------------------------------------------+
| active        | request        | Possible values: active, inactive                      |
+---------------+----------------+--------------------------------------------------------+

Example
^^^^^^^

To make the earning rule ``earningRule = 7d482776-318a-48dd-90cd-6b3f06a3f4e8`` active, use the method below:

.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/earningRule/7d482776-318a-48dd-90cd-6b3f06a3f4e8/active \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "active=1"

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.

.. note::

    The *earningRule = 7d482776-318a-48dd-90cd-6b3f06a3f4e8* id is an example value. Your value may be different.
    Check the list of all earningRules if you are not sure which id should be used.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 204 No Content



Get an earning rule's photo
---------------------------

To get an earning rule's photo, you need to call the ``/api/<storeCode>/earningRule/<earningRule>/photo`` endpoint with the ``GET`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    GET /api/<storeCode>/earningRule/<earningRule>/photo

+---------------+----------------+--------------------------------------------------------+
| Parameter     | Parameter type | Description                                            |
+===============+================+========================================================+
| Authorization | header         | Token received during authentication                   |
+---------------+----------------+--------------------------------------------------------+
| <storeCode>   | query          | Code of the store the earning rule belongs to.         |
+---------------+----------------+--------------------------------------------------------+
| <earningRule> | query          | Earning rule ID                                        |
+---------------+----------------+--------------------------------------------------------+

Example
^^^^^^^

To get the photo for earning rule ``earningRule = 000096cf-32a3-43bd-9034-4df343e5fd93``, use the method below:

.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/earningRule/000096cf-32a3-43bd-9034-4df343e5fd93/photo \
        -X "GET" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.

.. note::

    The *earningRule = 000096cf-32a3-43bd-9034-4df343e5fd93* id is an example value. Your value may be different.
    Check the list of all earning rules if you are not sure which id should be used.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. note::

    In the response you will get raw file content with a proper ``Content-Type`` header, for example:
    ``Content-Type: image/jpeg``.

Example Response
^^^^^^^^^^^^^^^^^^

The earning rule may not have a photo at all and you will receive the following response:

.. code-block:: text

    STATUS: 404 Not Found

.. code-block:: json

    {
      "error": {
        "code": 404,
        "message": "Not Found"
      }
    }



Remove an earning rule's photo
------------------------------

To remove an earning rule's photo, you need to call the ``/api/<storeCode>/earningRule/<earningRule>/photo`` endpoint with the ``DELETE`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    DELETE /api/<storeCode>/earningRule/<earningRule>/photo

+---------------+----------------+-----------------------------------------------+
| Parameter     | Parameter type | Description                                   |
+===============+================+===============================================+
| Authorization | header         | Token received during authentication          |
+---------------+----------------+-----------------------------------------------+
| <storeCode>   | query          | Code of the store the earning rule belongs to.|
+---------------+----------------+-----------------------------------------------+
| <earningRule> | query          | Earning rule ID                               |
+---------------+----------------+-----------------------------------------------+

Example
^^^^^^^

To remove the photo for earning rule ``earningRule = 000096cf-32a3-43bd-9034-4df343e5fd93``, use the method below:

.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/earningRule/000096cf-32a3-43bd-9034-4df343e5fd93/photo \
        -X "DELETE" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.

.. note::

    The *earningRule = 000096cf-32a3-43bd-9034-4df343e5fd93* id is an example value. Your value may be different.
    Check the list of all earning rules if you are not sure which id should be used.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK



Add a photo to an earning rule
------------------------------

To add a photo to an earning rule, you need to call the ``/api/<storeCode>/earningRule/<earningRule>/photo`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/<storeCode>/earningRule/<earningRule>/photo

+---------------+----------------+-----------------------------------------------+
| Parameter     | Parameter type | Description                                   |
+===============+================+===============================================+
| Authorization | header         | Token received during authentication          |
+---------------+----------------+-----------------------------------------------+
| <storeCode>   | query          | Code of the store the earning rule belongs to.|
+---------------+----------------+-----------------------------------------------+
| <earningRule> | query          | Earning rule ID                               |
+---------------+----------------+-----------------------------------------------+
| photo[file]   | request        | Absolute path to the photo                    |
+---------------+----------------+-----------------------------------------------+

Example
^^^^^^^

To add a photo to earning rule ``earningRule = 000096cf-32a3-43bd-9034-4df343e5fd93``, use the method below:

.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/earningRule/000096cf-32a3-43bd-9034-4df343e5fd93/photo \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "photo[file]=C:\fakepath\Photo.png"

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.

.. note::

    The *earningRule = 000096cf-32a3-43bd-9034-4df343e5fd93* id is an example value. Your value may be different.
    Check the list of all earning rules if you are not sure which id should be used.

.. note::

    The *photo[file]=C:\fakepath\Photo.png* is an example value. Your value may be different.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK



QR code
--------

This method allows calculating points using QR codes.
You need to call the ``/api/<storeCode>/earningRule/qrcode/customer/<customer>`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/<storeCode>/earningRule/qrcode/customer/<customer>

+----------------------------+----------------+------------------------------------------------------------------------+
| Parameter                  | Parameter type | Description                                                            |
+============================+================+========================================================================+
| Authorization              | header         | Token received during authentication                                   |
+----------------------------+----------------+------------------------------------------------------------------------+
| <storeCode>                | query          | Code of the store the earning rule and customer belong to.             |
+----------------------------+----------------+------------------------------------------------------------------------+
| <customer>                 | query          | Customer ID                                                            |
+----------------------------+----------------+------------------------------------------------------------------------+
| earningRule[code]          | request        | QR code                                                                |
+----------------------------+----------------+------------------------------------------------------------------------+
| earningRule[earningRuleId] | request        | *(optional)* UUID of the earning rule. If specified, only this one     |
|                            |                | rule will be executed.                                                 |
|                            |                | If omitted, all rules applicable to the customer will be executed      |
+----------------------------+----------------+------------------------------------------------------------------------+

Example Response
^^^^^^^^^^^^^^^^^^
.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/earningRule/qrcode/customer/00000000-0000-474c-b092-b0dd880c07e1 \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "earningRule[code]=abccode" \
        -d "earningRule[earningRuleId]=e378c813-2116-448a-b125-564cef15f932"
.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.

.. note::

    The *00000000-0000-474c-b092-b0dd880c07e1* customer UUID, *e378c813-2116-448a-b125-564cef15f932* earning rule UUID, *abccode* qr code are example values.
    Your values can be different.

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "points": 10
    }



Geolocation
-----------

To calculate points using geolocation, you need to call the ``/api/<storeCode>/earningRule/geolocation/customer/<customer>`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/<storeCode>/earningRule/geolocation/customer/<customer>

+----------------------------+----------------+------------------------------------------------------------------------+
| Parameter                  | Parameter type | Description                                                            |
+============================+================+========================================================================+
| Authorization              | header         | Token received during authentication                                   |
+----------------------------+----------------+------------------------------------------------------------------------+
| <storeCode>                | query          | Code of the store the earning rule and the customer belong to.         |
+----------------------------+----------------+------------------------------------------------------------------------+
| <customer>                 | query          | Customer ID                                                            |
+----------------------------+----------------+------------------------------------------------------------------------+
| earningRule[latitude]      | body           | Current customer's latitude. Positive and negative values can be used. |
+----------------------------+----------------+------------------------------------------------------------------------+
| earningRule[longitude]     | body           | Current customer's latitude. Positive and negative values can be used. |
+----------------------------+----------------+------------------------------------------------------------------------+
| earningRule[earningRuleId] | query          | *(optional)* UUID of the earning rule. If specified, only this one     |
|                            |                | geo rule will be executed.                                             |
|                            |                | If comitted, all rules applicable to the customer will be executed     |
+----------------------------+----------------+------------------------------------------------------------------------+


Example Response
^^^^^^^^^^^^^^^^^^
.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/earningRule/geolocation/customer/00000000-0000-474c-b092-b0dd880c07e1 \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "earningRule[latitude]=52.052240"
        -d "earningRule[longitude]=-21.046587"
        -d "earningRule[earningRuleId]=51283523-0760-474b-8c08-4ccd2b3a0f41"
.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.

.. note::

    The *00000000-0000-474c-b092-b0dd880c07e1* customer UUID, *83fe084b-3682-4ddb-bc10-c3c2373dfbcc* earning rule UUID,
    *52.052240, -21.046587* coordinates are example values.
    Your values can be different.

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "points": 1
    }
