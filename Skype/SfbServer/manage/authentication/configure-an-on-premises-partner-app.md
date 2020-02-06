---
title: 비즈니스용 Skype 서버에 대 한 온-프레미스 파트너 응용 프로그램 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: '요약: 비즈니스용 Skype 서버에 대 한 온-프레미스 파트너 응용 프로그램을 구성 합니다.'
ms.openlocfilehash: 3f8aa3bfc7407ccf6409d00c540cfeab724913ab
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818830"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="06fb9-103">비즈니스용 Skype 서버에 대 한 온-프레미스 파트너 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="06fb9-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="06fb9-104">**요약:** 비즈니스용 Skype 서버에 대 한 온-프레미스 파트너 응용 프로그램을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="06fb9-105">OAuthTokenIssuer 인증서를 할당 한 후에는 비즈니스용 Skype 서버 파트너 응용 프로그램을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="06fb9-106">(논의에 대 한 절차에 따라 Microsoft Exchange Server 2013 및 SharePoint가 파트너 응용 프로그램 역할을 하는 것으로 구성 되며, 선택 사항입니다.) 온-프레미스 파트너 응용 프로그램을 구성 하려면 먼저 다음 Windows PowerShell 스크립트를 복사 하 여 코드를 메모장 (또는 기타 텍스트 편집기)에 붙여 넣어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
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

<span data-ttu-id="06fb9-107">코드를 복사한 후를 사용 하 여 스크립트를 저장 합니다. PS1 파일 확장명 (예: C:\Scripts\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="06fb9-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="06fb9-108">이 스크립트를 실행 하기 전에 먼저 Exchange 2013 및 SharePoint 서버에서 사용 하 https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 는 http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 메타 데이터 Url과 메타 데이터 url을 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="06fb9-109">각 제품의 메타 데이터 URL을 식별 하는 방법에 대 한 자세한 내용은 Exchange 2013 및 SharePoint의 제품 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06fb9-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="06fb9-110">스크립트의 마지막 줄을 보면이 구문을 사용 하 여 Set CsOAuthConfiguration cmdlet이 호출 된다는 사실을 알게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="06fb9-111">Set-CsOAuthConfiguration을 호출할 때 Realm 매개 변수를 사용 하지 않았으므로 영역이 조직의 FQDN (정규화 된 도메인 이름) (예: litwareinc.com)으로 자동 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-111">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com).</span></span> <span data-ttu-id="06fb9-112">영역 이름이 조직 이름과 다른 경우 다음과 같이 영역 이름을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-112">If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="06fb9-113">이러한 변경 작업을 수행한 후에는 스크립트를 실행 하 고 비즈니스용 Skype 서버 관리 셸에서 스크립트 파일을 실행 하 여 Exchange 2013와 SharePoint를 파트너 응용 프로그램으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="06fb9-114">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-114">For example:</span></span>
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="06fb9-115">Exchange 2013 및 SharePoint Server가 설치 되어 있지 않은 경우에도이 스크립트를 실행할 수 있습니다. SharePoint Server가 설치 되어 있지 않은 경우에도 파트너 응용 프로그램으로 SharePoint Server를 구성 하는 경우에는 문제가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="06fb9-116">이 스크립트를 실행 하면 다음과 같은 오류 메시지가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="06fb9-117">이 오류 메시지는 일반적으로 스크립트에 지정 된 Url 중 하나가 유효 하지 않은 경우 (즉, 메타 데이터 Url 중 하나가 실제 메타 데이터 URL이 아닌 경우)에 해당 하는 두 가지 중 하나를 의미 합니다. 또는 2) 메타 데이터 Url 중 하나에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-117">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted.</span></span> <span data-ttu-id="06fb9-118">이 문제가 발생 하면 Url이 올바르며 액세스할 수 있는지 확인 하 고 스크립트를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-118">If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="06fb9-119">비즈니스용 Skype Server 용 파트너 응용 프로그램을 만든 후에는 비즈니스용 Skype 서버를 Exchange 2013 파트너 응용 프로그램으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="06fb9-120">Configure-EnterprisePartnerApplication 스크립트를 실행 하 여 Exchange 2013에 대 한 파트너 응용 프로그램을 구성할 수 있습니다. 비즈니스용 Skype 서버용 메타 데이터 URL을 지정 하 고 비즈니스용 Skype 서버가 새 파트너 응용 프로그램 임을 표시 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="06fb9-121">비즈니스용 Skype 서버를 Exchange 용 파트너 응용 프로그램으로 구성 하려면 Exchange 관리 셸을 열고 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fb9-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


