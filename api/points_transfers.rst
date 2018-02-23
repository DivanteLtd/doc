Points transfers
================

These endpoints will allow you to easily manage Points transfers.

	
Method will return a complete list of Points transfers
------------------------------------------------------

To retrieve a paginated list of Points transfers you will need to call the ``/api/points/transfer`` endpoint with the ``GET`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    GET  /api/points/transfer

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| customerFirstName                   | query          | *(optional)* First Name                           |
+-------------------------------------+----------------+---------------------------------------------------+
| customerLastName                    | query          | *(optional)* Last Name                            |
+-------------------------------------+----------------+---------------------------------------------------+
| customerPhone                       | query          | *(optional)* Customer Phone                       |
+-------------------------------------+----------------+---------------------------------------------------+
| customerEmail                       | query          | *(optional)* Customer Email                       |
+-------------------------------------+----------------+---------------------------------------------------+
| customerId                          | query          | *(optional)* Customer ID                          |
+-------------------------------------+----------------+---------------------------------------------------+
| state                               | query          | *(optional)* Possible values: active, expired     |
+-------------------------------------+----------------+---------------------------------------------------+
| type                                | query          | *(optional)* Possible values: adding, spending    |
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


Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/points/transfer \
        -X "GET" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."
		
.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an exemplary value.
    Your value can be different. Read more about :doc:`Authorization in the </authorization>`.
	

Exemplary Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

{
  "transfers": [
    {
      "pointsTransferId": "e82c96cf-32a3-43bd-9034-4df343e5f433",
      "accountId": "e4c4b479-be5f-44cd-bbaa-7d6a90e53564",
      "customerId": "00000000-0000-474c-b092-b0dd880c07e2",
      "customerFirstName": "Jane",
      "customerLastName": "Doe",
      "customerLoyaltyCardNumber": "0000",
      "customerEmail": "user-temp@oloy.com",
      "customerPhone": "111112222",
      "createdAt": "2018-01-21T09:45:06+0100",
      "value": 100,
      "state": "expired",
      "type": "adding",
      "issuer": "system",
      "expireAt": "2018-02-20T09:45:06+0100"
    },
    {
      "pointsTransferId": "40922a3e-c0dd-4c69-87be-613fafe5076c",
      "accountId": "adbdb586-317b-4bed-8cc0-346199064d45",
      "customerId": "00000000-0000-474c-b092-b0dd880c07e1",
      "customerFirstName": "John",
      "customerLastName": "Doe",
      "customerEmail": "user@oloy.com",
      "customerPhone": "11111",
      "createdAt": "2018-02-22T09:54:28+0100",
      "value": 5,
      "state": "active",
      "type": "adding",
      "issuer": "system",
      "expireAt": "2018-03-24T09:54:28+0100"
    },
    {
      "pointsTransferId": "37a248d8-a3ee-40a6-a491-513210557573",
      "accountId": "f6c87121-942e-4f79-9734-0fe863ee9fee",
      "customerId": "57524216-c059-405a-b951-3ab5c49bae14",
      "customerFirstName": "Tomasz",
      "customerLastName": "Test80",
      "customerEmail": "tomasztest80@wp.pl",
      "createdAt": "2018-02-22T08:45:22+0100",
      "value": 1,
      "state": "active",
      "type": "adding",
      "issuer": "system",
      "expireAt": "2018-03-24T08:45:22+0100"
    }
  ],
  "total": 3
  
  	
Method will return a complete list of Points transfers (seller)
---------------------------------------------------------------

To retrieve a paginated list of Points transfers you will need to call the ``/api/seller/points/transfer`` endpoint with the ``GET`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    GET  /api/seller/points/transfer
	
+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| customerFirstName                   | query          | *(optional)* First Name                           |
+-------------------------------------+----------------+---------------------------------------------------+
| customerLastName                    | query          | *(optional)* Last Name                            |
+-------------------------------------+----------------+---------------------------------------------------+
| customerPhone                       | query          | *(optional)* Customer Phone                       |
+-------------------------------------+----------------+---------------------------------------------------+
| customerEmail                       | query          | *(optional)* Customer Email                       |
+-------------------------------------+----------------+---------------------------------------------------+
| customerId                          | query          | *(optional)* Customer ID                          |
+-------------------------------------+----------------+---------------------------------------------------+
| state                               | query          | *(optional)* Possible values: active, expired     |
+-------------------------------------+----------------+---------------------------------------------------+
| type                                | query          | *(optional)* Possible values: adding, spending    |
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

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/points/transfer \
        -X "GET" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."
		
.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an exemplary value.
    Your value can be different. Read more about :doc:`Authorization in the </authorization>`.
	

Exemplary Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

{
  "transfers": [
    {
      "pointsTransferId": "e82c96cf-32a3-43bd-9034-4df343e5f433",
      "accountId": "e4c4b479-be5f-44cd-bbaa-7d6a90e53564",
      "customerId": "00000000-0000-474c-b092-b0dd880c07e2",
      "customerFirstName": "Jane",
      "customerLastName": "Doe",
      "customerLoyaltyCardNumber": "0000",
      "customerEmail": "user-temp@oloy.com",
      "customerPhone": "111112222",
      "createdAt": "2018-01-21T09:45:06+0100",
      "value": 100,
      "state": "expired",
      "type": "adding",
      "issuer": "system",
      "expireAt": "2018-02-20T09:45:06+0100"
    },
    {
      "pointsTransferId": "e82c96cf-32a3-43bd-9034-4df343e5f333",
      "accountId": "e4c4b479-be5f-44cd-bbaa-7d6a90e53564",
      "customerId": "00000000-0000-474c-b092-b0dd880c07e2",
      "customerFirstName": "Jane",
      "customerLastName": "Doe",
      "customerLoyaltyCardNumber": "0000",
      "customerEmail": "user-temp@oloy.com",
      "customerPhone": "111112222",
      "createdAt": "2018-02-19T09:45:06+0100",
      "value": 100,
      "state": "active",
      "type": "spending",
      "comment": "Example comment",
      "issuer": "system",
      "expireAt": "2018-03-21T09:45:06+0100"
    },
    {
      "pointsTransferId": "e82c96cf-32a3-43bd-9034-4df343e5f111",
      "accountId": "e4c4b479-be5f-44cd-bbaa-7d6a90e53564",
      "customerId": "00000000-0000-474c-b092-b0dd880c07e2",
      "customerFirstName": "Jane",
      "customerLastName": "Doe",
      "customerLoyaltyCardNumber": "0000",
      "customerEmail": "user-temp@oloy.com",
      "customerPhone": "111112222",
      "createdAt": "2018-01-21T09:45:05+0100",
      "value": 100,
      "state": "expired",
      "type": "adding",
      "issuer": "system",
      "expireAt": "2018-02-20T09:45:05+0100"
    }
  ],
  "total": 3
}


Method allows to add points to customer.
----------------------------------------

To add a new points you will need to call the ``/api/points/transfer/add`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/points/transfer/add

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[customer]                  | query          | Customer ID                                       |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[points]                    | query          | How many points customer can get                  |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[comment]                   | query          | *(optional)* Comment                              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer                            | query          | *(optional)* Points transfer ID                   |
+-------------------------------------+----------------+---------------------------------------------------+

    curl http://localhost:8181/api/points/transfer/add \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."
		
.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an exemplary value.
    Your value can be different. Read more about :doc:`Authorization in the </authorization>`.
	

Exemplary Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

	{
	  "pointsTransferId": "32132863-3d1e-4a94-8bb4-6e42e3c96c0b"
	}


Method allows to spend customer points.
---------------------------------------

To spend customer points you will need to call the ``/api/points/transfer/spend`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/points/transfer/spend
	
+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[customer]                  | query          | Customer ID                                       |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[points]                    | query          | How many points customer can get                  |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[comment]                   | query          | *(optional)* Comment                              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer                            | query          | *(optional)* Points transfer ID                   |
+-------------------------------------+----------------+---------------------------------------------------+
	

    curl http://localhost:8181/api/points/transfer/spend \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."
		
.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an exemplary value.
    Your value can be different. Read more about :doc:`Authorization in the </authorization>`.
	

Exemplary Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

	{
	  "pointsTransferId": "b97a31fe-9bc9-4fff-a467-487f2c316371"
	}
	
	
Method allows to cancel specific points transfer.
-------------------------------------------------

To cancel specific points transfer you will need to call the ``/api/points/transfer/{transfer}/cancel`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/points/transfer/{transfer}/cancel
	
+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer                            | query          | Points transfer ID                                |
+-------------------------------------+----------------+---------------------------------------------------+
	
    curl http://localhost:8181/api/points/transfer/{transfer}/cancel \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."
		
.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an exemplary value.
    Your value can be different. Read more about :doc:`Authorization in the </authorization>`.
	

Exemplary Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

	[]