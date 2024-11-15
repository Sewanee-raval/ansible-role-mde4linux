---

ANSIBLE-ROLE-MDE4LINUX
=========

This role will install or uninstall the Microsoft Defender Endpoint for Linux on Ubuntu and RHEL machines.

Requirements
------------

This role requires that the Microsoft Defender OnBoarding file be downloaded and made available within the files directory.
The directions for downloading the onboarding package can be found on Microsoft's website at: https://learn.microsoft.com/en-us/defender-endpoint/linux-install-with-ansible#download-the-onboarding-package

Role Variables
--------------

The primary role variable that must be set is the EDR Channel variable.

edr_distro: rhel  # ansible_distribution
edr_version: 8    # ansible_distribution_major_version
edr_channel: insiders-fast # insiders-fast, insiders-slow, prod

The choice of the channel determines the type and frequency of updates that are offered to your device. Devices in insiders-fast are the first ones to receive updates and new features, followed later by insiders-slow, and lastly by prod.

When installing MDE4L it is suggested to have at least machine with an edr_channel set to insiders-fast 

Switching the channel after the initial installation requires the product to be reinstalled. To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.


Dependencies
------------

N/A at this time

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```bash
ansible-playbook tests/test.yml -i tests/inventory --extra-vars '{"var":"value"}'
```

License
-------

GPLv3

Author Information
------------------

Raymond Val [sewanee-raval]
