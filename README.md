```
ionic cordova plugin add cordova-plugin-geolocation --variable GEOLOCATION_USAGE_DESCRIPTION="To locate you"
npm install --save @ionic-native/geolocation@5.0.0-beta.21
```


<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyA_uVKWprjIgPURNhl1v9zzTPLQJIBdi6I"></script>

```
import { Geolocation } from '@ionic-native/geolocation/ngx';
const rta = await this.geolocation.getCurrentPosition();
const myLatLng = {
  lat: rta.coords.latitude,
  lng: rta.coords.longitude
};
console.log(myLatLng);
```

````
const mapEle: HTMLElement = document.getElementById('map');
// create map
const map = new google.maps.Map(mapEle, {
  center: myLatLng,
  zoom: 12
});
````

````
google.maps.event
.addListenerOnce(map, 'idle', () => {
  // loaded
});
````

````
import { LoadingController } from '@ionic/angular';
const loading = await this.loadingCtrl.create();
loading.present();
loading.dismiss();
````

````
const marker = new google.maps.Marker({
  position: {
    lat: myLatLng.lat,
    lng: myLatLng.lng
  },
  zoom: 8,
  map: map,
  title: 'Hello World!'
});
````