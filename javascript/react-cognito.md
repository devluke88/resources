---
description: Some boilerplate code
---

# React Cognito

```
  const [apiData, setApiData] = useState([]);
  const CREATE_ORDER_API_ENDPOINT = "https://api.dev.rectanagi.com/v1/orders";
  const [isLoading, setIsLoading] = useState(false);
  const [error, setError] = useState(null);
  const callApi = async () => {
    try {
      const response = await fetch(CREATE_ORDER_API_ENDPOINT, {
        method: "POST",
        headers: {
          Authorization: `Bearer ${user.signInUserSession.accessToken.jwtToken}`,
        }
      });

      if (response.status === 200) {
        const data = await response.text();
        setApiData(data);
      } else {
        console.error("Error calling the API:", response.statusText);
      }
    } catch (error) {
      console.error("Error calling the API:", error);
    }
  };
  useEffect(() => {
    callApi();
  }, []);


    const handleCreateOrder = async (priceId) => {
    const token = (await Auth.currentSession()).getAccessToken().getJwtToken();
    console.log("token: ", token);
    setIsLoading(true);
    await fetch(CREATE_ORDER_API_ENDPOINT, {
      method: "POST",
      headers: {
        "Content-Type": "application/json"
        // authorization: `Bearer ${token}`
      },
      body: JSON.stringify({
        price_id: priceId,
        user_email: user.signInUserSession.idToken.payload.email
      })
    })
      .then(response => {
        setIsLoading(false);
        if (!response.ok) {
          throw new Error(`Request failed with status: ${response.status} and ${response.message}`);
        }
        return response.json();
      })
      .then(data => {
        if (data && data.checkout_url) {
          const redirectUrl = data.checkout_url;
          // Initiate the redirection using window.location.href
          window.location.href = redirectUrl;
        } else {
          throw new Error("Redirect URL not found in the response.");
        }
      })
      // .catch(error => new Error("Redirect URL not found in the response.: ", error));
      .catch(error => console.log("ERROR: ", error));
  };
```
