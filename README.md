# Kyle's Van

- [Amazon wish list](https://smile.amazon.com/hz/wishlist/ls/2UEBMG8BSWQO9?ref_=wl_dp_add_item_to_list)
- [Load calculations Google Sheet](https://docs.google.com/spreadsheets/d/1SxFsj5xPVnLx2yNxhEEx6YxGCWcOJNQjID-fIwVTki8/edit#gid=0)

## System Overview

- 1x 100ah Lifepo4 Battery
  - 1,200wh
- 1x 1500w Inverter
- Charge controller:
  - 705W solar / 12v batteries = 58.75A

## Components

### Existing Components

- Inverter: Vanner 20-1050CUL
- Panels x2:
  - Sharp Solar Module ND-Q235Q2
    - Pmax: 235W
    - Voc: 37.2V
    - Short circuit current: 9.59A
    - Vpmax: 30.1V
    - Ipmax: 7.8A
    - Parallel config:
      - 2 panels:
        - Volatage: 30.1V
        - Current: 15.6A
      - 3 panels:
        - Volatage: 30.1V
        - Current: 23.4A
  - Peak is 470w
  - Realistic is 470 x 0.7 = 329w
  - Need minimum of 39amp charge controller: 470w / 12v = 39 amps
  - Charge times
    - Perfect: 1200w / 470w = 2.5h
    - Realistic: 1200w / 329w = 3.6h

## Appliances

- Fridge: 120w
- Fan: 60w
- Inverter: 2300w
- Kettle: 1500w
- Toilet: 1.6w
- Laptop: 65w
- Vitamix: 1440w

## Load calculations

[See Google Sheet](https://docs.google.com/spreadsheets/d/1SxFsj5xPVnLx2yNxhEEx6YxGCWcOJNQjID-fIwVTki8/edit#gid=0)

- Fridge: 120w
- Toilet: 1.6w
- Laptop: 65w
- Kettle: 1500w
- MaxxAir Fan: 60w
- Phone charging: 50w/hr
- Vitamix: 720w/hr

## Design Notes

- Have individual disconnect switches for every appliance (so you can reduce
  draw if needed)
- Have a master disconnect switch for the entire system
- Have a cutoff switch for the solar panels
  - Always disconnect solar when messing with the charging system

## Electrical Notes

- 6g wire for charge system (or less/thicker)

#### What size fuse do I need?

125% amp rating for fuses: `10amp appliance => 12.5amp +/- fuse`

#### What's the difference between series and parallel for solar panels?

- **Series**:
  - Daisy-chain
  - Voltage goes up, amps stay same
  - Must be same amp rating!
  - If any panels are shaded, the output is reduced a lot
- **Parallel**:
  - Connect all positives and all negatives together
  - Amps go up, volts the same
  - Must be same voltage!
  - Can handle partial shade on some panels without impacting charging

#### How do I calculate how big my solar/battery arrays need to be?

- Plan for 3-5 days of autonomy only on battery
  - TOTAL LOAD x HOURS USED = WATT HOURS
  - WATT HOURS \* 3-5 days = BATTERY SIZE (round to nearest battery size)
  - BATTERY SIZE / 5 HOURS SUN/DAY = SOLAR ARRAY SIZE (round up)
  - Example:
    - 120w x 5hr = 600wh
    - 600wh x 3 days = 1800wh (round to 2,400wh)
    - 2,400wh / 5hr = 480wh -> 600wh (round up)
