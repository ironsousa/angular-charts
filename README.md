# angular-charts

## CONFIG STEPS

```
1. sudo npm install -g @angular/cli
2. ng new charts
3. cd charts
4. npm install chart.js --save
5. npm install --save rxjs-compat
6. npm install -g json-server
```

## ADDING DATA TO FAKE JSON-SERVER

```
gitpod /workspace/angular-charts/charts $ cat > data.json
{
  "results": [
  {
      "month": "Jan",
      "price": "180"
  },
  {
    "month": "Feb",
    "price": "200"
  },
  {
    "month": "March",
    "price": "210"
  },
  {
    "month": "April",
    "price": "190"
  },
  {
    "month": "May",
    "price": "240"
  },
  {
    "month": "June",
    "price": "230"
  },
  {
    "month": "July",
    "price": "260"
  },
  {
    "month": "Aug",
    "price": "210"
  },
  {
    "month": "Sept",
    "price": "300"
  }]
}
```
## Starting Server

```
json-server --watch data.json --port 4000
```

### OUTPUT
```
  Resources
  http://localhost:4000/results

  Home
  http://localhost:4000
```
