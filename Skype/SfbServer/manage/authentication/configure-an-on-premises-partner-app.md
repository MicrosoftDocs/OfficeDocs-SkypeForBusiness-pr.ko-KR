---
title: 비즈니스용 Skype 서버에 대한 프레미스 파트너 응용 프로그램 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: '요약: 비즈니스용 Skype 서버에 대한 프레미스 파트너 응용 프로그램을 구성합니다.'
ms.openlocfilehash: 82db666dbbd94fdae8a99bca13954d33d6d5805f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828438"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="b73e7-103">비즈니스용 Skype 서버에 대한 프레미스 파트너 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="b73e7-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="b73e7-104">**요약:** 비즈니스용 Skype 서버에 대한 프레미스 파트너 응용 프로그램을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="b73e7-105">OAuthTokenIssuer 인증서를 할당한 후 비즈니스용 Skype 서버 파트너 응용 프로그램을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="b73e7-106">설명할 절차는 Microsoft Exchange Server 2013 및 SharePoint가 파트너 응용 프로그램 역할을 하도록 구성됩니다(선택 사항). 프레미스 파트너 응용 프로그램을 구성하려면 먼저 다음 Windows PowerShell 스크립트를 복사하고 코드를 메모장(또는 다른 텍스트 편집기)에 붙여 넣는 것으로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
```PowerShell
if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
   {
       Remove-CsPartnerApplication app
   }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
        
if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
           }
     }

$shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
        
if ($shp -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
    }
else
    {
       if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.sharepoint
  
             New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl https://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
            }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="b73e7-107">코드를 복사한 후 를 사용하여 스크립트를 저장합니다. PS1 파일 확장명(예: C:\Scripts\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="b73e7-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="b73e7-108">이 스크립트를 실행하기 전에 메타데이터 URL과 https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 Exchange 2013 및 SharePoint 서버에서 사용하는 메타데이터 URL로 각각 바꾸야 http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="b73e7-109">각 제품의 메타데이터 URL을 식별하는 방법에 대한 자세한 내용은 Exchange 2013 및 SharePoint의 제품 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b73e7-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="b73e7-110">스크립트의 마지막 줄을 보면 다음 구문을 사용하여 Set-CsOAuthConfiguration cmdlet이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="b73e7-111">Realm 매개 변수를 호출할 때 사용되지 Set-CsOAuthConfiguration 영역은 조직의 FQDN(정식 도메인 이름)(예: litwareinc.com)으로 자동 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-111">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com).</span></span> <span data-ttu-id="b73e7-112">사용자 이름이 조직 이름과 다른 경우 다음과 같이 해당 이름에 다음을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-112">If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="b73e7-113">이러한 변경 내용을 적용한 후 비즈니스용 Skype 서버 관리 셸 내에서 스크립트 파일을 실행하여 스크립트를 실행하고 Exchange 2013과 SharePoint를 파트너 응용 프로그램으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="b73e7-114">예제:</span><span class="sxs-lookup"><span data-stu-id="b73e7-114">For example:</span></span>
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="b73e7-115">Exchange 2013과 SharePoint Server를 모두 설치하지 않은 경우에도 이 스크립트를 실행할 수 있습니다. 즉, SharePoint Server를 설치하지 않은 경우에도 SharePoint Server를 파트너 응용 프로그램으로 구성하면 문제가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="b73e7-116">이 스크립트를 실행하면 다음과 같은 오류 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="b73e7-117">이 오류 메시지는 일반적으로 두 가지 중 하나를 의미합니다. 1) 스크립트에 지정된 URL 중 하나가 유효하지 않습니다(즉, 메타데이터 URL 중 하나는 실제 메타데이터 URL이 아닐 수 있습니다). 또는 2) 메타데이터 URL 중 하나에 연결하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-117">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted.</span></span> <span data-ttu-id="b73e7-118">이 경우 URL이 올립하고 액세스할 수 있는지 확인하고 스크립트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-118">If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="b73e7-119">비즈니스용 Skype 서버의 파트너 응용 프로그램을 만들고 나면 비즈니스용 Skype 서버를 Exchange 2013의 파트너 응용 프로그램으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="b73e7-120">스크립트 응용 프로그램을 실행하여 Exchange 2013에 대한 파트너 응용 프로그램을 구성할 수 Configure-EnterprisePartnerApplication.ps1. 비즈니스용 Skype 서버의 메타데이터 URL을 지정하고 비즈니스용 Skype 서버가 새 파트너 응용 프로그램으로 표시하기만하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="b73e7-121">비즈니스용 Skype 서버를 Exchange의 파트너 응용 프로그램으로 구성하기 위해 Exchange 관리 셸을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e7-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


