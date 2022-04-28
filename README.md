## Naver Map wep page

https://rkdogo08.github.io/map_final/  
https://rkdogo08.github.io/map_final/#1A387F,2D69A4,1A0753,2DDAF3

## Using Naver Map in MATLAB

```matlab
gps_map = gps_data(1:2,:);

gps_t = "";
n = 1.8;              % 플로팅 텀 (n번에 한개씩) 총 380개
end_i = min(380, length(gps_map));

for i = 1:n:end_i
    ind = round(i);
%     lat1 = dec2hex(floor(gps_map(1,i)));
%     lon1 = dec2hex(floor(gps_map(2,i)));
    lat2 = dec2hex(floor(mod(gps_map(1,ind)*10,1)*1e7));
    lon2 = dec2hex(floor(mod(gps_map(2,ind)*10,1)*1e7));


    gps_t = gps_t + num2str(lat2)+",";
    gps_t = gps_t + num2str(lon2)+",";
end
gps_t = strip(gps_t,'right',',');

dos("start chrome https://rkdogo08.github.io/map_final/#"+gps_t);
% #1A387F,2D6964,1A3753,2D6AF3
% #0.0171,0.0298,0.0171,0.0298
% #37.5171,127.1298,37.5171,127.1298
```


[Naver Map Api](https://www.ncloud.com/product/applicationService/maps)
