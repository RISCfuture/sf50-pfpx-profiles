# Cirrus SF50 Profiles for PFPX

This project contains PFPX performance profiles and aircraft templates for the
Cirrus SF50 VisionJet, Generations 1 and 2. You can use these profiles and
templates with PFPX to do accurate dispatch and flight planning.

PFPX is a dispatch and flight planning tool intended for flight simulation use.
You can use it to plan flights, estimate time and fuel burn, maintain a schedule
of upcoming flights, keep a database of preferred routes, and create dispatch
sheets including weather briefings and navigation logs. It's similar to SimBrief
which is also used in the sim world, and ForeFlight flight planning, which is
typically used by real-world VisionJet pilots.

## Installation

Unpack the archive, and place the `Aircraft`, `AircraftTemplates`, and
`AircraftTypes` directories in your `C:\Users\Public\Public Documents\PFPX`
directory. (This directory should exist if you've already installed PFPX.)

## What's Included?

You get the following:

**Aircraft types for the G1 and G2 VisionJet.** These aircraft types include
accurate performance data, directly sourced from the AFM for both aircraft. The
performance data includes climb, cruise, and descent profiles, as well as basic
weight and equipment data.

**Aircraft templates for the G1 and G2 VisionJet.** You can use these aircraft
templates to create your own VisionJet aircraft. These templates will pre-fill
most of the Aircraft fields, including fuel burn and costs, equipment, alternate
requirements, etc.

**N300DG, a 2018 Cirrus VisionJet.** This happens to be my VisionJet. You can
check it out as a basis for creating a realistic VisionJet aircraft profile. It
has all relevant fields filled out, including ATC data, operational data, cost
information, etc.

## How to Use

You can duplicate N300DG, or create your own G1 or G2 VisionJet using **Add New
Aircraft From Template…**. Note that although the template fills in many of the
fields, it doesn't fill in all of them. Reference N300DG for an example of
values you can fill in for the remaining fields.

## Aircraft Notes

In this section, I will discuss operational notes and caveats for different PFPX
aircraft fields and functions, to help you more realistically use this template.

### Weights and Loading

Max takeoff weight for the SF50 is 6,000 pounds. Due to rounding errors when
working between pounds and kilograms, I set the maximum takeoff weight in the
performance profile to 6,001 pounds. The aircraft template and N300DG correctly
use 6,000 pounds, however.

The VisionJet can equip up to 7 seats, 5 adult seats and 2 child seats limited
to 90 lb (41 kg) each. All but two of the seats are easily removable. The
removable seats **are _not_ included in the dry operating weight [DOW]**. Most
of the time, to save weight, the VisionJet is not flown with all seven seats
installed. If you are flying with more than the two front seats, you should add
the weight of the additional seats to the cargo weight.

Typical seat weights are 30 lb (14 kg) for the adult seats (3, 4, and 5) and
15 lb (7 kg) for the child seats (6 and 7). The actual weights for the actual
seats for N300DG are listed in the operational notes for the PFPX aircraft
record.

IPS fluid, which is used to de-ice the windshield and radome, is also not
included in the DOW. A full tank of IPS fluid weighs 28 lb (13 kg), and should
be included in the cargo weight when flight planning. The minimum fluid quantity
allowed for dispatch into known icing conditions is 1.0 gal, or 9 lb (4 kg).

Most privately-owned aircraft include an array of equipment and supplies
throughout the cabin and baggage, including covers and pins, manuals and
documents, an AOG (aircraft on ground) kit, perhaps survival supplies, etc. In
N300DG, these supplies add up to around 25 lb (11 kg) of extra weight that must
be added to the DOW.

### Fuel

VisionJet pilots are taught to land with no fewer than 70 gallons (470 lb, 213
kg) onboard. Because of this, a typical planning scenario, where no alternates
are required\*, would be to reduce the number of required alternates in PFPX to
None, and then set the **Remaining Fuel** field to **470 lb** (213 kg).

\*Per 14 CFR 91.169(c), an alternate is not required if the weather at
the destination (at ±1 hour around ETA) is forecast to be better than 3 miles
visibility and ceilings above 2,000 feet.

If an alternate is required, you would typically set the number of alternates
required in PFPX to one, and then accept the higher fuel requirements.

Taxi fuel at sea level is 12 gallons per hour (81 pph, 37 kg/hr).

### Cruise Profiles

Performance is provided for two cruise profiles, **Maximum Continuous Thrust
(MCT)** and **Maximum Range Cruise (MRC)**.

When flying an MCT profile, the pilot keeps the thrust lever in the MCT detent
for the entire climb and cruise. (For a low-altitude cruise, below about 10,000
feet, it will be necessary to maintain a thrust setting below MCT to avoid
exceeding V<sub>MO</sub> [250 knots]).

When flying an MRC profile, the pilot references the MRC thrust setting
published in the cruise tables for the current altitude and ISA deviation.

For practical purposes, MCT is essentially the only cruise profile flown. An MRC
profile is too slow to be worth the fuel savings. The MRC profile should be used
when doing alternate or holding planning, however.

### Descent Profiles

Three descent profiles are included. All three are flown at Mach 0.51 above
18,300 feet, transitioning to 245 KIAS at 18,300 feet. (18,300 feet is always
the changeover altitude in the VisionJet.)

The three descent profiles represent -2.8°, -3.7°, and -4.6° of flight path
angle. These represent approximately 1500 fpm, 2000 fpm, and 2500 fpm descent
rates, respectively. -3.7° is the default VNAV setting and what you will get if
you program in a VNAV descent normally.

### Optimum Altitudes

Optimum cruising altitudes were indeed calculated for the performance profile;
however, the no-wind optimum altitude always ended up being the maximum cruising
altitude (FL280 for the G1; FL310 for the G2). This is typical of very light
jets. Ignoring wind, your best range and best endurance will be found at your
maximum cruising altitude.

### Equipment

When you purchase a VisionJet, you are able to specify which optional equipment
should be installed. This in turn will change Item 10 and Item 18 on the flight
plan form, which are captured under the Configuration tab in the PFPX aircraft
profile:

**Equipment (10a)**: The best possible equipment code for a G2 VisionJet is
`SBDFGRWY`. G1 VisionJets are not RVSM approved and should therefore drop the
`W`. The ADF (`F`) and the DME (`D`) are optional, so many VisionJets do not
have them equipped.

**ADS capability (10b)**: The best possible surveillance code for a VisionJet is
`B2U2`. VisionJets sold in Europe (such as N300DG) do not typically have ADS-B
In installed (since there is no ADS-B In in Europe), and so should be downgraded
to `B1U1`.

**FAA code**: G2 VisionJets with RVSM should use `L`; G1 VisionJets should use
`G`.

**PBN**: The only area navigation system onboard a VisionJet is its GPS. Because
of this, only the GPS navigation codes should be used. The VisionJet is approved
for RNP-10 oceanic navigation (`A1`), as well as domestic enroute navigation
down to RNP-1 (`B2C2D2`). The VisionJet is approved for RNP approaches with
baro-aided VNAV (`S2`). It is conceivable that a private VisionJet pilot would
apply for and receive authorization to conduct RNP-AR approaches (`T2`), but
very unlikely. Most likely only commercial operators would bother getting RNP-AR
certification.

**SUR**: The VisionJet includes both 1090 MHz and UAT transceivers, and so
should include `SUR/260B 282B` in flight plans.

**PER**: The VisionJet qualifies for approach category B (91–120 knots).

**RVR**: Most private VisionJet pilots are not qualified to conduct special
authorization ILS approaches (category II and category III approaches);
therefore, RVR should be set to 550m (Cat I). It is conceivable but very
unlikely that a private owner would apply for and receive Cat II qualification,
but a commercial operator might. A Cat II qualified operator could set this
field to 300m. The GFC 700 autopilot in the VisionJet is not certified for
Cat III operations.

### Operating Costs

Mostly for fun, I have included operating cost values in the PFPX profile. The
fixed hourly costs are calculated on an assumption of flying 250 hours per year,
typical for a private owner and frequent flyer. The variable hourly costs are
left at zero because they are negligible, as explained below.

Nearly every VisionJet owner pays for JetStream Concierge, Cirrus's
all-inclusive ownership plan. The plan covers virtually all ownership expenses,
other than fuel and oil. This includes foreseen and unforeseen maintenance
events, normal upkeep such as oil and tire changes, subscriptions to services
like satellite phone and navigation data/charts, and even annual recurrent
training for the pilot. The cost of the Concierge level is $270,000 every three
years.

Because of this, I have estimated a typical fixed ownership cost to be the cost
of JetStream Concierge, plus a typical insurance rate ($27,000 per year for a
private owner of respectable experience), plus a typical hangar rental rate
($250 per month). Obviously these fixed costs can vary widely, especially if the
aircraft is used for Part 135 air taxi or charter flights, in which case
insurance will be significantly more expensive, and maintenance and other
ownership costs will be completely different. But on the other hand, an aircraft
that flies for a Part 135 company will fly a lot more than 250 hours per year.

Variable costs include only fuel and oil. The price of oil is negligible (less
than $1 per hour) and PFPX does its fuel cost calculation separately, so
variable cost is left at zero. If you are simulating Part 135 ops, you will also
need to include the cost of crew (salaries, etc.), and fill a value in for the
delay costs (money you're leaving on the table by not picking up more
passengers).

If you want to price out your flights, simply make sure to fill in a value into
the **Fuel Price** field when dispatching, and then in the Summary tab under
Results, you should see the final cost of the flight. It will be the fixed cost
plus the cost of fuel.

Note that most jet pilots do not pay "sticker price" for fuel. So even if you go
on AirNav and see that Jet A- is, say, $3.89 per gallon at some airport FBO,
if the VisionJet pilot has a fuel card, such as through CAA, they would likely
pay a lower negotiated rate. These rates are usually 50¢ to $1 cheaper than the
published rate.

Obviously, part 135 operators would have their own fuel contracts and pay
significantly less than sticker price for fuel too.

## Typical Flight Planning Steps

1. Enter the basic information into the PFPX Flight tab: origin, destination,
   aircraft, route, etc.
2. Fill in the payload. PFPX will use the average general aviation passenger
   weights you specified in Settings. Be sure to include the weight of
   additional seats, IPS fluid, and other equipment (as described above) in the
   **Cargo** field.
3. Set the **Remaining Fuel** field to **470 lb** (213 kg).
4. Determine if an alternate is necessary using the 1-2-3 rule. If one is not
   necessary, set the **Altns required** field to **None**. Otherwise, choose
   alternates normally.
5. If you want to plan delays/holding, re-dispatching, etc., do that under the
   Advanced tab.
6. Compute your flight!

### Why Does it Keep Saying the Flight is Overweight??

Because it's a VisionJet! With full fuel, the SF50 is essentially a two-person
aircraft, especially two typically-hefty Americans. If you are carrying a
family-sized load, you must take less fuel, probably around 220 to 250 gallons
max.

Full fuel minus reserves in the VisionJet is nearly three hours of flying at
MCT, which will take you about 900 NM (1700 km) ignoring winds. This is a good
leg length for a VisionJet, which doesn't have a lavatory. It gives an
opportunity for passengers to get out and stretch their legs for a bit before
continuing on. Plus, FBOs are generally well-appointed and know how to take care
of passengers during quick turns.

With a family-sized load on board, you may be looking at something 1.5-hour
legs. Your typical sim pilot, especially one accustomed to flying 12-hour legs
in the 777, may balk -- but trust me! It's really not that bad. You get used to
it…
