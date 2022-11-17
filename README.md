# Balena Custom Device Support (CDS)

**Note: This is a WIP as we determine how best to lay out and productize the CDS process.**

## Overview

The outcome of CDS is a production-grade custom version of balenaOS built for your Linux device of choice, with ongoing support including test-and-release of upgraded OS versions.

- For a device to be compatible with the balenaCloud platform, it needs to run balenaOS, our minimal Linux distribution built with Yocto and designed to run containers
- Our device support team will build a custom version of balenaOS specifically for your device type, making sure we meet all of your hardware requirements. We will periodically build, test, and release upgrades to the OS as well.
- Your custom device type and its associated custom device OS will be available to download in the balenaCloud dashboard.

## Included with Custom Device Support

- **Initial development:** build and test a custom balenaOS image for your device type
- **Ongoing support:**
  - Upgrading: we will periodically upgrade your device type’s host OS to incorporate new features, security patches, bug fixes, kernel upgrades, etc.
  - Testing: we will test every new version of the host OS on your exact device in our testing rig
  - Releasing: we will release every new version of the host OS so that it’s available for download via the balenaCloud dashboard
  - Troubleshooting: our device support team will assist you with questions, issues, or feature requests you have for your device’s OS

**Note:** We use an automated testing rig to validate the OS releases. Once we have the patches for the board we will add your hardware to the testing rig in order to have the automated tests run with each PR. In the future, we intend to ship testing rigs to CDS customers for faster turn around time on new release testing. The tests balena runs are here: <https://github.com/balena-os/meta-balena/tree/master/tests/suites>; There are three categories of tests: cloud tests, OS tests, and host OS updates tests.

## Pricing

We will evaluate and provide a quote for your specific board, depending on the effort and complexity required to support it. We will need you to send our team a board (and any peripherals) for the evaluation.

The cost for this evaluation process is **$1,000 USD**, which will be credited towards the initial development cost, should you decide to enter into a custom device support contract.

Note that after we evaluate your board, we will still need two more boards for our device support team, which we will keep for the development phase and ongoing support.

To learn more about pricing and ongoing costs, see the [CDS section on balena's pricing page](https://www.balena.io/pricing/#custom-device-support).

## Misc Notes

- Peripherals (e.g. modems) may require additional custom support and testing from the balena team, and may increase the cost of providing custom device support.
- Additional hardware revisions may also require an increase in the cost.
- If you require that your custom device is confidential / private to your team (i.e. not available for all users to download via the balenaCloud dashboard), talk to us about private device type options
- Other custom device support options may be available; please let us know if you’d like to discuss tailor-made custom device support plans and packages
- The correct Tier pricing can only be confirmed once your device has gone through initial evaluation

## Requirements

Minimum device specs:

- 1GB RAM or greater
- 4GB Storage or greater
- Storage must be block-based eMMC or SD card; flash-based not supported
- Linux kernel v4.0 or higher

Documentation:

- Basic Hardware Specs - We'll want to know all pertinent information including processor, available RAM, storage etc and all associated details.
- Vendor Documentation - Any documentation you are aware of, particularly documentation which provides a detailed description of your device's boot process.
- Datasheet - Preferably one that discusses your device's boot process in as much detail as possible
- Logo - A logo that would appear in the balenaCloud UI for your device type

Software:

- BSP Layer - This is preferably a vendor-supported distribution of a Yocto BSP. Please also include components versions, location of sources, and license details where applicable. BSP support (including but not limited to bootloader, kernel, and firmware) must be provided by the customer and/or OEM. Balena is not responsible for maintaining or providing these components.
- If Yocto support does not exist, we will communicate in more detail with the assigned Technical Point of Contact throughout the process about exact needs for your specific board, but at a minimum we will require the following:
  - Bootloader sources
  - Kernel sources
  - Bootloader and Kernel configs required for this hardware
  - Documentation for provisioning an OS image
  - Documentation on booting options, including:
    - how the hardware boots from microSD, USB, eMMC, etc.
    - if any dip switch or jumpers need to be set to configure where the boot firmware loads the bootloader from, etc.
  - Firmware for connectivity, such as Bluetooth or Wi-Fi
- Existing Linux Support - If this is not already included in the documentation above, let us know if there are any known linux distributions which both your application stack and this board run on (eg Ubuntu 20.04). Provide details and/or links to repos where applicable.

More Information:

- Technical Point of Contact: Name and email address of the primary technical point of contact on your team. We will interface with this person to ask specific questions along the way and to help with testing and validating early versions of the OS images we will produce.
- Minimum Peripherals Requirements: Does this custom image need to support certain connectivity methods, cellular modems, or other peripherals, etc?
- Timeline: When do you need to have a working version of balenaOS images and when do you expect to have devices running balenaOS in a production-like fashion?
- Legal: Are there any export control regulations that could apply to this board? Or any other licensing or legal considerations that might require special handling?
- Confidentiality Requirements: Specify any requirements you have around the confidentiality of the balenaOS repos, base images, and any other mentions of your device in a public settings. In particular:
  - Do you want this device-type to be **Public** and available for any balena customer to download and use from the balenaCloud dashboard or do you wish it be **Private** and only available to people in your Organization of the balenaCloud dashboard?
  - Do you want the code created to implement this device-type available for everyone to view and make use of (i.e. in the [https://github.com/balena-os](https://github.com/balena-os) GitHub organization) or will you require the code to be Private?
  - Note that balena charges the cost for managing a Private GitHub repository if necessary, in addition to any other applicable maintenance fees.

**Note:** A CDS customer will also confirm these aspects when going through our information gathering form when initiating evalution: [https://balena.typeform.com/to/OXJXXb](https://balena.typeform.com/to/OXJXXb)

## Sending Devices to Balena

- Three boards sent to our team in Galati for development and testing, to be replaced with new hardware revisions as needed.
- Please complete [this form](https://forms.gle/xzGfC9SksrYcmGja6) to schedule a DHL pickup for the three devices and power supplies.
- Alternatively, you can ship the equipment over to our team in Athens, and they will forward it to our Galati, Romania office. Please make sure to mark the package and add a shipping note with **"Route to Galati (YOUR COMPANY NAME)"** so the team will know to schedule a DHL pickup as soon as they receive it. Here is the address to ship the equipment:

      Attn: Stefanos Sakellariou
      Balenaio Ltd
      Evrimedontos 4, 2nd Floor, 10435, Athens Greece

**Note 1:** These devices must be the same hardware version you are taking into production.

**Note 2:** Due to our devices being routed to our hardware team in Romania, the shipping and customs review process can take several weeks. However, we will provide a tracking number for your reference once the pickup process has been completed.

## Step 1: Evaluation - Description of Work

Evaluation of your custom hardware is the first step in Balena’s Custom Device Support process. It allows balena engineers to scope the work required to develop a balenaOS image on your behalf. After scoping is complete, balena will provide an official quote which includes the price tier for initial onboarding and ongoing maintenance (if desired) of that hardware onto balenaCloud, as described here: [https://www.balena.io/pricing/#custom-device-support](https://www.balena.io/pricing/#custom-device-support)

In order to complete this work, Balena will require submission of the following form to ensure all relevant documentation and software components are shared with our engineers and scoping can begin as quickly as possible upon arrival of your hardware: [https://balena.typeform.com/to/OXJXXb](https://balena.typeform.com/to/OXJXXb)

Additionally, please review the information below and, if you are not already including these details in the documentation you share with us via the above link, please share it with your Customer Success representative via email.

## Step 2: Full Custom Device Support - Description of Work

Balena will develop a production-grade, custom version of balenaOS, built specifically for a CDS customer's hardware. In addition to this initial onboarding effort, balena will be providing ongoing support, including updates to the custom device-type in the case of hardware changes, support for device-type specific questions in our Support queue, as well as test-and-release of upgraded balenaOS versions.

## Maintainership Agreement: Terms and Conditions

As part of balena’s maintenance of the new device-type, the following is required from a CDS customer:

- Notification of any hardware changes, including new hardware shipped to balena for ongoing OS testing when necessary
- Notification of any changes to bootloader sources, kernel versions, firmware versions, etc. as well as access to those files for inclusion with future versions of the device-type
- BSP support (including but not limited to bootloader, kernel, and firmware) must be provided by the customer and/or OEM. Balena is not responsible for maintaining or providing these components.

Future contact with balena can be made in the following ways:

- Submitting issues to the related balena GitHub repository (<https://github.com/balena-os/[your-device-type]>)
- Submitting tickets through balena’s Support chat system (in the balenaCloud dashboard)
- Emailing your Customer Success contact at balena

If balena reaches out to the customer for questions about upcoming OS releases which require the customer's input, and balena does not receive response from the customer within 6 months, balena reserves the right to remove this device-type from our dashboard and halt all actions related to its maintenance, or to make it a publicly available Device Type.

After discontinuance of support for this hardware by the manufacturer, or end of support for the Yocto version required by this hardware, balena commits to keeping the device-type on the platform for up to two years, but with no further updates outside of critical security fixes if possible.
