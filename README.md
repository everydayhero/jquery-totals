# jquery-totals

A simple jQuery plugin that fetches total funds raised (for a page, campaign or charity) from the [everydayhero API](http://developer.everydayhero.com/totals/) and displays the result in a targetted HTML element.


### Simple Usage

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
  </head>
  <body>
    <div id="amount"></div>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"></script>
    <script src="https://d2h3g7rbnequ8a.cloudfront.net/edh_totals/edh_totals-0.0.2.min.js"></script>
    <script>
      $(function() {
        $('#amount').getEDHTotals({ ids: ['au-0', 'us-1'] });
      });
    </script>
  </body>
</html>
```

### Options

| Option    | Type      | Default Value      | Description        |
| --------- | --------- | ------------------ | ------------------ |
| `type`    | string    | `'campaign'`       | Can be `'campaign'`, `'charity'` or `'page'`. |
| `ids`     | array     | `['au-0']`         | Insert ids (of the same type) as an array. Totals for each provided id will be summed together. |
| `callback` | function | none               | Callback to run after the total has been retrieved. `this` contains an object including the currency symbol, a total in cents and the formatted total to do as you want with. |


### Using a callback

A callback can be used to retreive an object that contains the currency symbol, a total in cents and the formatted total. This can be useful if you need to display the returned amount in a different format or tamper with the returned total in some way after displaying it.

```js
<script>
  $(function() {
    $('#amount').getEDHTotals({
      type: 'campaign',
      ids: ['us-0'],
      callback: function() {
        console.log(this); // Logs the returned object
      }
    });
  });
</script>
```

**Latest CDN Version:**

Minified: https://d2h3g7rbnequ8a.cloudfront.net/edh_totals/edh_totals-0.0.2.min.js
