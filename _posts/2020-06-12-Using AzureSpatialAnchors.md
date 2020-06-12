---
layout: post
title: "Using AzureSpatialAnchors"
subtitle: "Error: Application did not provide valid credentials and therefore could not authenticate with the Cloud Service."
date: 2020-06-12 16:00
---

**Error description:**

I want to use AzureSpatialAnchors, so I tried the codes from [Tutorial: Step-by-step instructions to create a new HoloLens Unity app using Azure Spatial Anchors](https://docs.microsoft.com/en-us/azure/spatial-anchors/tutorials/tutorial-new-unity-hololens-app?tabs=UnityPackage#putting-everything-together). 

You should be able to see a white sphere, then anchor it by air tapping and it turns orange, after a while it becomes blue, which means it has been synced to cloud.

However, what I saw was an orange sphere turned to red.

**What I did**

I built the scene, debugged the .sln file in VS, and got an Error:Application did not provide valid credentials and therefore could not authenticate with the Cloud Service.

This is an ApplicationNotAutenticated Error (check [CloudSpatialErrorCode Enum](https://docs.microsoft.com/en-us/dotnet/api/microsoft.azure.spatialanchors.cloudspatialerrorcode)).

**Solution**

I added 

‘protected string SpatialAnchorsAccountDomain = "@myDomain(use my own domain)";’

after

'protected string SpatialAnchorsAccountKey = "Set me";'


and this time it works as expected!

