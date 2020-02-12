---
title: 비즈니스용 Skype 서버 2019 제어판 인증 스크립트
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/23/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: OAuth 프로토콜을 통해 Office 365를 사용 하 여 SFB 2019 제어판 인증을 구성 하는 도우미 스크립트입니다.
ms.openlocfilehash: ad6c41c70cc885ca8eee2a19e7dcc4173ef714c2
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887727"
---
# <a name="skype-for-business-server-2019-control-panel-authentication-script"></a>비즈니스용 Skype 서버 2019 제어판 인증 스크립트

이 스크립트는 새 제어판에 대 한 설정의 일부로 비즈니스용 Skype 서버 2019 누적 업데이트 1을 설치한 후에 실행 되어야 합니다. 이 스크립트는 Azure에서 Azure AD 응용 프로그램을 만듭니다. 이렇게 하면 새 제어판에서 OAuth를 사용 하 여 Office 365에 로그인 하는 데 도움이 됩니다.

```powershell
<#
 .SYNOPSIS
 Helper script to configure SFB 2019 control panel authentication with Office 365 via OAuth protocol.

 .DESCRIPTION
 Copyright (c) Microsoft Corporation. All rights reserved.

 THIS CODE IS MADE AVAILABLE AS IS, WITHOUT WARRANTY OF ANY KIND. THE ENTIRE RISK
 OF THE USE OR THE RESULTS FROM THE USE OF THIS CODE REMAINS WITH THE USER.

 .EXAMPLE
 Creates a native client application on azure active directory with name "MACP"
#>

Write-Host "Getting external FQDN of SFB pools"
$externalFqdns=(Get-CsService -WebServer).ExternalFqdn

Write-Host "Getting internal FQDN of SFB pools"
$internalFqdns=(Get-csService -WebServer).poolfqdn

$replyUrls=New-Object System.Collections.Generic.List[string]

Write-Host "Generating Redirect URIs for modern admin control panel"
#Generating replyUrls using external fqdns
foreach ($externalFqdn in $externalFqdns) {
  if ($externalFqdn -ne $null) {
    $replyUrls.Add('https://' + $externalFqdn + '/macp/iframe.html');
  }
}

#Generating replyUrls using internal fqdns
foreach($internalFqdn in $internalFqdns) {
  if ($internalFqdn -ne $null) {
    $replyUrls.Add('https://' + $internalFqdn + '/macp/iframe.html');
  }
}

if (Get-Module -ListAvailable -Name "AzureAd") {
  Write-Host "AzureAD module exists"
}
else {
  Write-Host "Installing AzureAD module";
  Install-Module -name AzureAD
}

$uniqueReplyUrls = $replyUrls | sort -Unique

#Importing AzureAd module
Write-Host "Importing AzureAD module";
Import-module AzureAD

Write-Host "Connect to Azure AD using your azure tenant admin credentials"
Connect-azureAd

$requiredResourceAccess1 = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
$requiredResourceAccess1.ResourceAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.ResourceAccess" -ArgumentList "921df259-ef26-44e6-b99e-69e13226d635","Scope"
$requiredResourceAccess1.ResourceAppId = "39624784-6cbe-4a60-afbe-9f46d10fdb27"

$requiredResourceAccess2 = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
$requiredResourceAccess2.ResourceAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.ResourceAccess" -ArgumentList "311a71cc-e848-46a1-bdf8-97ff7156d8e6","Scope"
$requiredResourceAccess2.ResourceAppId = "00000002-0000-0000-c000-000000000000"

$requiredResourceAccess = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.RequiredResourceAccess]
$requiredResourceAccess.Add($requiredResourceAccess1)
$requiredResourceAccess.Add($requiredResourceAccess2)

$azureADApplication=Get-AzureADApplication -Filter "DisplayName eq 'MACP'"

if ($azureADApplication -eq $null) {
  Write-Host "Creating Azure AD application for modern admin control panel (MACP)"
  $azureADApplication = New-AzureADApplication -DisplayName "MACP" -PublicClient $true -Oauth2AllowImplicitFlow $true -ReplyUrls $uniqueReplyUrls -RequiredResourceAccess $requiredResourceAccess
}
else {
  Write-Host "Azure ad application for modern admin control panel (MACP) already exists with displayName: " $azureADApplication.DisplayName ". Updating the properties"
  Write-Host $uniqueReplyUrls
  Set-AzureADApplication -ObjectId $azureADApplication.ObjectId -PublicClient $true -Oauth2AllowImplicitFlow $true -ReplyUrls $uniqueReplyUrls
}

Write-Host "Updating the AzureAD application Id in CMS"
Set-CsHybridConfiguration -ClientId $azureADApplication.AppId
```
