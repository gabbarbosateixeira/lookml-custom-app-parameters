# Looker Heat Pump Calculator

This repository contains the LookML code for a custom Heat Pump Calculator application built entirely within Looker. It serves as a practical example for customers demonstrating how to leverage Looker's modeling layer to create interactive, data-driven applications.

The application allows users to input various details about their home and receive an estimated cost and size for a new heat pump system. This provides a dynamic and engaging experience for users while showcasing the power of Looker beyond traditional business intelligence.

![Heat Pump Calculator App](image.png)

---

## How It Works

The calculator is built upon a single LookML `view` that cleverly uses parameters as user inputs. When a user changes a filter, like the "Year Built" or "Total Square Footage", the application dynamically recalculates the estimates in real-time.

The core logic is based on a **base cost** calculation which is then adjusted by a series of **multipliers**. Each multiplier corresponds to a user-selectable parameter, allowing for a nuanced and accurate final estimate.

---

## Key Components & Features

### 1. User Inputs (Parameters)

Instead of filtering existing data, we use LookML **`parameters`** to capture user input. These are defined as interactive filters on the dashboard.

*   Total Square Footage
*   Year Built
*   Number of Stories
*   Finished Basement (Yes/No)
*   Home Insulation (Yes/No)
*   Primary Heating Fuel
*   And several others...

**Example LookML for a parameter:**

```lookml
parameter: p_year_built {
  label: "Year Built"
  type: string
  allowed_value: { value: "2010+" }
  allowed_value: { value: "1990 to 2009" }
  allowed_value: { value: "1970 to 1889" }
  allowed_value: { value: "Before 1970" }
}
