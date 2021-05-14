<details open>
<summary>**Create New Query**</summary>
<br>
  Store query configuration creating a new entry.

* **URL**

  /shipping-metrics-get-api/queries

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
 
   `id=[integer]`


* **Sample Post:**

  ```json
    {	
	"id": "1",
	"type": "bigquery",
	"description": "Test",
	"status": "enable",
	"response_type": "json",
	"sql_query": "SELECT METRICS_AUDIT.CALCULATOR_CONTROLLER FROM `meli-bi-data.SHIPPING_BI.BT_SHP_MT_CALCULATOR_CONTROLLER` WHERE DATE(AUD_INS_DTTM) = \"2021-05-07\" LIMIT 10",
	"created_at": "2021-05-07T03:46:34.615866",
	"created_by": "abasile"
}
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ id : 12, name : "Michael Bloom" }`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "User doesn't exist" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

</details>
<details open>
<summary>Want to ruin the surprise?</summary>
<br>
**Show User**
----
  Returns json data about a single user.

* **URL**

  /users/:id

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
 
   `id=[integer]`

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ id : 12, name : "Michael Bloom" }`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "User doesn't exist" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/users/1",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
</details>
