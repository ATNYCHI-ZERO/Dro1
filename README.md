# Dro1Goal / constraints

Cool a high-power onboard computer or small ESCs/GPU while keeping drone flight capable. Target thermal load 20–80 W. Keep added mass ≤ 500–700 g for medium consumer quad.

Parts (recommendations)

Airframe: medium frame rated for +2 kg MTOW.

Flight controller + ESCs: your usual stack. Keep ESCs isolated from coolant.

Propulsion: motors/props sized for extra payload. Aim for 30–40% thrust margin.

Battery: LiPo 4S–6S sized for payload. Expect reduced flight time.

Radiator: slim 120×25 mm aluminum drone radiator (≈100–180 g).

Fan: 120 mm low-profile fan or two 40–60 mm fans if space limited (25–60 g).

Pump: micro brushless centrifugal or gear pump, 4–12 V, flow 0.5–1.0 L/min, weight 60–150 g. Choose low-vibration model.

Liquid cold-plate / waterblock: small custom block for SBC/SoC or wrapped copper cold plate. Use thermal interface material.

Tubing & fittings: 4–6 mm ID flexible fuel tubing plus low-profile push fittings and hose clamps.

Reservoir: small sealed reservoir or expansion tank (20–50 ml).

Coolant: 50/50 distilled water + propylene glycol with corrosion inhibitor. Optionally use dielectric coolant if available.

Sensors & wiring: temp sensors (DS18B20 or thermistor), pump power lead, quick-disconnect for coolant.

Mounting hardware: vibration dampers, zip ties, foam, epoxy mounts.

Leak protection: conformal coat for electronics, waterproof enclosures for SBC, drip trays (thin foam) under critical boards.

Estimated mass & power (typical)

Radiator+fan ~150 g. Pump ~80 g. Tubing+fittings ~50 g. Coolant ~80–150 g. Mounts ~40 g.

Added mass ≈400–600 g.

Pump power ~3–7 W. Fan(s) 3–6 W. Total electrical draw ~6–15 W.

Design choices and tradeoffs

Onboard radiator vs offboard radiator: on-board is compact but heavy. Consider mounting radiator vertically to use propwash for cooling.

Single loop for CPU only reduces tubing and mass. Full ESC+CPU loop increases complexity and failure points.

Use redundant pump if cooling critical. Redundancy costs weight.

Assembly steps (high level)

Plan mass distribution. Place radiator where propwash or airflow assists cooling. Keep center of gravity central.

Mount waterblock to target (SBC, GPU, ESC heat sink). Use thermal paste and secure with low-profile bracket.

Route tubing in smooth curves. Avoid kinks. Use vibration-isolated clamp points. Keep tubing away from props.

Place pump near CG if possible. Minimize suction head. Use proper inlet orientation.

Install radiator and fan. Ensure airflow direction moves air through radiator during hover.

Connect reservoir with small bleed port at high point. Fill and bleed loop until no air pockets.

Power pump with regulated supply or UBEC. Add fuse and switch for pump/fan. Isolate pump ground from noise-sensitive sensors.

Conformal-coat exposed boards and fit electronics in sealed boxes with breather for pressure changes.

Secure quick-disconnect fittings for rapid removal. Add drip containment under electronics.

Ground and EMI: keep coolant and metal contacts isolated from signal grounds. Use braided shielding if necessary.

Testing procedure

Bench test pump and fan dry run for 10–30 min. Check flow, leaks, and temperature delta.

Leak test under low pressure. Paper towel under joints for 30+ min.

Thermal test with full CPU load while on test stand. Log temps. Verify safe margins.

Tethered hover tests with minimal throttle. Monitor temps and vibrations.

Short flight tests progressively increasing duration and payload.

Safety and reliability

Use non-conductive coolant or ensure robust conformal coating. Water causes shorts.

Fit automatic pump-cutoff if temp sensor fails.

Design for safe flight if pump fails: ensure components can survive brief thermal excursion.

Keep tubing away from prop arc. Use rigid guards.

Be aware added mass reduces flight time and maneuverability.

Performance note

Expect coolant loop to lower CPU/GPU temps by 10–30°C depending on power and radiator area. Flight time will drop proportionally to added mass and parasitic power draw.

Legal and operational note

Follow local UAV regulations. Do not arm or fly a modified airframe until fully tested.

If you want I will:

produce a compact BOM with specific part SKUs and approximate prices; or

sketch a loop diagram (tube routing, radiator placement, pump/reservoir location) sized for a 40 W thermal load.

Which of those now.

You said:
Ok copy paste block 
ChatGPT said:
# COPY–PASTE BLOCK — WATER-COOLED DRONE BUILD PLAN

# =========================
# 1. PARTS LIST
# =========================
parts = {
    "airframe": "Quadcopter frame rated for 2+ kg MTOW",
    "motors": "Brushless motors sized for extra payload (e.g. 2216/920KV)",
    "escs": "30A+ ESC stack, separate from coolant loop",
    "battery": "4S–6S LiPo with enough capacity for extra 600 g mass",
    "pump": "Micro brushless centrifugal pump, 12V, 0.5–1.0 L/min, ~80 g",
    "radiator": "120 mm slim aluminum radiator (~150 g)",
    "fan": "120 mm or dual 60 mm low-profile fans (3–6 W draw)",
    "waterblock": "Small copper/aluminum cold-plate for SBC/CPU",
    "tubing": "4–6 mm ID flexible tubing, silicone or PU",
    "reservoir": "20–50 ml sealed mini tank",
    "coolant": "50/50 distilled water + propylene glycol (or dielectric coolant)",
    "sensors": "DS18B20 temp sensors or thermistors",
    "mounts": "Vibration dampers, zip ties, brackets",
    "protection": "Conformal coating + waterproof electronics enclosure"
}

# =========================
# 2. SYSTEM STATS
# =========================
system_stats = {
    "added_mass": "≈400–600 g",
    "power_draw": "≈6–15 W (pump + fans)",
    "thermal_load": "20–80 W target dissipation",
    "cooling_gain": "≈10–30 °C drop vs air only"
}

# =========================
# 3. ASSEMBLY STEPS
# =========================
assembly = [
    "Mount waterblock on CPU/GPU/SBC with thermal paste",
    "Route tubing smoothly, avoid kinks, keep clear of props",
    "Place pump near CG, minimize suction head",
    "Mount radiator vertical in propwash path",
    "Install small reservoir at high point for bleeding",
    "Fill and bleed loop until bubble-free",
    "Wire pump + fan via UBEC (fused, switched)",
    "Coat electronics with conformal spray + seal housing",
    "Add quick-disconnect fittings for tubing",
    "Leak test with paper towel under joints for 30+ min"
]

# =========================
# 4. TESTING SEQUENCE
# =========================
testing = [
    "Bench test pump/fan alone for 30 min",
    "Leak check under pressure, no air pockets",
    "Run CPU/GPU load, log temps",
    "Hover tethered at low throttle, watch temps",
    "Short flights with gradual duration increase"
]

# =========================
# 5. SAFETY NOTES
# =========================
safety = [
    "Use non-conductive coolant if possible",
    "Conformal coat all nearby PCBs",
    "Ensure tubing secure and guarded from props",
    "Design so flight is safe if pump fails briefly",
    "Observe UAV laws before flight"
]


This is a ready-to-run block. Would you like me to also make you a schematic loop diagram (ASCII) showing pump → block → radiator → reservoir → pump?
