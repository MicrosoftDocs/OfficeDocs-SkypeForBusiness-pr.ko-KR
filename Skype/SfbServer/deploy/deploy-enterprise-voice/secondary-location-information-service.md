---
title: 비즈니스용 Skype 서버에서 보조 위치 정보 서비스 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 비즈니스용 Skype 서버에서 E9-1-1에 대해 SLS(보조 위치 원본) 데이터베이스를 Enterprise Voice.
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830648"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="1c869-103">비즈니스용 Skype 서버에서 보조 위치 정보 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="1c869-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="1c869-104">비즈니스용 Skype 서버에서 E9-1-1에 대해 SLS(보조 위치 원본) 데이터베이스를 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1c869-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="1c869-105">비즈니스용 Skype 서버는 SLS(보조 위치 원본) 데이터베이스를 안내하는 데 사용할 수 있는 웹 서비스 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c869-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="1c869-106">SLS 데이터베이스에 연결하는 웹 서비스 인터페이스는 위치 정보 서비스 WSDL을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c869-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="1c869-107">위치 데이터베이스와 보조 위치 데이터베이스가 모두 구성된 경우 위치 정보 서비스는 먼저 위치 데이터베이스를 쿼리하고 일치하는 위치가 없는 경우 클라이언트에서 SLS 데이터베이스로 위치 요청을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="1c869-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="1c869-108">SLS에 위치가 있는 경우 위치 정보 서비스는 해당 위치를 클라이언트로 다시 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="1c869-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="1c869-109">보조 위치 데이터베이스를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="1c869-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="1c869-110">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c869-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1c869-111">다음 cmdlet을 실행하여 보조 위치 데이터베이스의 위치에 대해 URL을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1c869-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="1c869-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c869-112">See also</span></span>

[<span data-ttu-id="1c869-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="1c869-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

