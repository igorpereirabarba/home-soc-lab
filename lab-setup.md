# Lab Setup

This file documents the setup process for the Home SOC Lab.

## Step 1: Install VirtualBox

VirtualBox will be used to run virtual machines for the lab environment.

## Step 2: Create Virtual Machines

Planned virtual machines:

- Windows 10 or Windows 11
- Ubuntu Server
- Kali Linux
- Wazuh Server

## Step 3: Configure Lab Networking

The virtual machines will be configured on a safe internal or NAT network so they can communicate inside the lab.

## Step 4: Install Wazuh

Wazuh will be installed as the SIEM platform to collect and review security alerts.

## Step 5: Install Wazuh Agents

Agents will be installed on:

- Windows VM
- Ubuntu Server VM

## Step 6: Generate Test Activity

Planned test activity:

- Failed Windows login attempts
- Nmap scan from Kali Linux
- Failed SSH login attempts
- Suspicious PowerShell activity

## Step 7: Review and Document Alerts

Alerts will be reviewed in Wazuh and documented using SOC-style investigation reports.
