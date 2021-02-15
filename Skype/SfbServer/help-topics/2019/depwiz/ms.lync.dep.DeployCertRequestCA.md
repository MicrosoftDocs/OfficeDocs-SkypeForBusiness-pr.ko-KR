---
title: 인증서 요청(인증 기관)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: CA(인증 기관) 선택 페이지에서 온라인 CA(인증 기관)(일반적으로 내부 네트워크에 있는 서버)에 인증서를 요청할 때 다음 두 가지 옵션이 제공됩니다.
ms.openlocfilehash: 8744471569c76e8f8196cda41ca398c48205fea8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830368"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="93778-103">인증서 요청(인증 기관)</span><span class="sxs-lookup"><span data-stu-id="93778-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="93778-104">**CA(인증 기관) 선택** 페이지에서 온라인 CA(인증 기관)(일반적으로 내부 네트워크에 있는 서버)에 인증서를 요청할 때 다음과 같은 두 가지 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="93778-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="93778-105">환경에서 감지된 목록에서 CA 선택</span><span class="sxs-lookup"><span data-stu-id="93778-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="93778-106">다른 인증 기관 지정</span><span class="sxs-lookup"><span data-stu-id="93778-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="93778-107">첫 번째 옵션을 선택하면 해당 환경에서 검색된 모든 Windows Server 기반 인증 기관이 포함된 드롭다운 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="93778-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="93778-108">인증서에 적합한 인증 기관을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93778-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="93778-109">선택해야 하는 CA를 확인하려면 CA 관리자에게 문의해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93778-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="93778-p102">두 번째 옵션을 선택하는 경우 인증서에 사용할 인증 기관의 FQDN(정규화된 도메인 이름) 및 CA 인스턴스를 입력합니다. 이 옵션은 사용하려는 CA가 Windows Server 기반 CA는 아닌 경우에 적합하지만, Windows Server 기반 CA에 대해서도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="93778-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="93778-112">인증서 요청을 정상적으로 수행하는 데 필요한 그룹 구성원 자격을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93778-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="93778-113">일반적으로 인증 기관의 권한 요구 사항은 서버에 비즈니스용 Skype 서버를 설치하기 위한 요구 사항과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="93778-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="93778-114">CA 관리자에게 인증서를 요청하기 위한 요구 사항을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="93778-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

