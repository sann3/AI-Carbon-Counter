# AI-Carbon-Counter
Count the amount of carbon used for creating an AI model using Impact framework](https://if.greensoftware.foundation) and display in Hugging face

## Required input params
- `timestamp` - When the training for started
- `duration` - how much took to complete the training in seconds
- `cloud/instance-type` - Cloud instance name understandable by [cloud-metadata plugin](https://github.com/Green-Software-Foundation/if-plugins/blob/main/src/lib/cloud-metadata/README.md)
- `cloud/vendor` - Cloud vendor like azure, gcp, aws understandable by [cloud-metadata plugin](https://github.com/Green-Software-Foundation/if-plugins/blob/main/src/lib/cloud-metadata/README.md)
- `cloud/region` - Cloud regin where the machines were located cloud/region understandable by [cloud-metadata plugin](https://github.com/Green-Software-Foundation/if-plugins/blob/main/src/lib/cloud-metadata/README.md)
- `cpu/utilization` - If you know approximate usage percentage, otherwise go with 100

## Other information
WattTime API requires activation of subscription before usage. Please refer to the [WattTime website](https://watttime.org/docs-dev/data-plans/) for more information.

Create a `.env` file in the IF project root directory. This is where you can store your WattTime authentication details. Your `.env` file should look as follows:

**Required Parameters:**

```txt
WATT_TIME_USERNAME: <your-username>
WATT_TIME_PASSWORD: <your-password>
```


## How to run
```txt
install node

npm install -g "@grnsft/if-plugins"

npm install -g "@grnsft/if-unofficial-plugins"

ie --manifest ./ai_carbon_counter.yml --output output
```

The final output will be available in output file. Look for carbon variable for the carbon usage in grams.
