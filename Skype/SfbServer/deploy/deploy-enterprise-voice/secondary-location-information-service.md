---
title: 비즈니스용 Skype 서버에서 보조 위치 정보 서비스 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 비즈니스용 Skype Server Enterprise Voice에서 E9-1에 대 한 SLS (보조 위치 원본) 데이터베이스를 구성 합니다.
ms.openlocfilehash: 47dd4015cde79536323cee3edc04ed546459a3f0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240401"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="60fa6-103">비즈니스용 Skype 서버에서 보조 위치 정보 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="60fa6-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="60fa6-104">비즈니스용 Skype Server Enterprise Voice에서 E9-1에 대 한 SLS (보조 위치 원본) 데이터베이스를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="60fa6-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="60fa6-105">비즈니스용 Skype Server는 위치 정보 서비스를 보조 위치 원본 (SLS) 데이터베이스에 가리키는 데 사용할 수 있는 웹 서비스 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="60fa6-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="60fa6-106">SLS 데이터베이스에 연결 하는 웹 서비스 인터페이스는 위치 정보 서비스 WSDL을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60fa6-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="60fa6-107">위치 데이터베이스와 보조 위치 데이터베이스가 모두 구성 되어 있는 경우 위치 정보 서비스는 위치 데이터베이스에 먼저 쿼리 하 고 일치 하는 항목이 없으면 클라이언트의 위치 요청을 SLS 데이터베이스에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="60fa6-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="60fa6-108">위치가 SLS에 있는 경우에는 위치 정보 서비스에서 해당 위치를 다시 클라이언트로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="60fa6-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="60fa6-109">보조 위치 데이터베이스를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="60fa6-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="60fa6-110">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="60fa6-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="60fa6-111">다음 cmdlet을 실행 하 여 보조 위치 데이터베이스의 위치에 대 한 URL을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="60fa6-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="60fa6-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60fa6-112">See also</span></span>

[<span data-ttu-id="60fa6-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="60fa6-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

