---
title: 인증서 요청(반환됨)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 온라인 인증서 요청 상태 페이지에는 온라인 인증서 요청의 생성 및 발급에 성공한 중요한 정보가 표시됩니다. 이 페이지에서는 인증서를 고유하게 식별하는 인증서 지문을 제공합니다. 기본적으로 이 인증서를 비즈니스용 Skype 서버 인증서 사용에 할당하는 확인란이 선택되어 있습니다. 완료를 클릭하면 인증서 요청 생성 단계에서 정의한 목적을 위해 인증서가 비즈니스용 Skype 서버에 자동으로 할당됩니다. 기본적으로 인증서가 할당되는 용도는 다음과 같습니다.
ms.openlocfilehash: 8d7d1dc5013505b7874bccd2ee415f9211713e70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801838"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="ad1b9-107">인증서 요청(반환됨)</span><span class="sxs-lookup"><span data-stu-id="ad1b9-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="ad1b9-108">온라인 **인증서 요청 상태** 페이지에는 온라인 인증서 요청의 생성 및 발급에 성공한 중요한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad1b9-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="ad1b9-109">이 페이지에서는 인증서를 고유하게 식별하는 인증서 지문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad1b9-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="ad1b9-110">기본적으로 이 인증서를 비즈니스용 **Skype 서버** 인증서 사용에 할당하는 확인란이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad1b9-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="ad1b9-111">완료를 클릭하면 인증서 요청 생성 단계에서 정의한 목적을 위해 인증서가 비즈니스용 Skype 서버에 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad1b9-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="ad1b9-112">기본적으로 인증서가 할당되는 용도는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad1b9-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="ad1b9-113">MTLS(상호 전송 계층 보안)에 대한 서버 기본값 - 클라이언트 및 기타 서버에 대한 연결</span><span class="sxs-lookup"><span data-stu-id="ad1b9-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="ad1b9-114">웹 서비스 내부 - TLS/SSL(전송 계층 보안/SSL)에 대한 내부 웹 서비스 사이트의 Secure Sockets Layer 연결</span><span class="sxs-lookup"><span data-stu-id="ad1b9-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="ad1b9-115">웹 서비스 외부 - TLS/SSL에 대한 외부 웹 서비스 사이트의 클라이언트 및 서버 연결</span><span class="sxs-lookup"><span data-stu-id="ad1b9-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="ad1b9-116">**인증서 세부 정보 보기** 를 클릭하여 인증서를 보면 인증서의 속성이 의도한 대로인지 확인하고 인증서가 서버에서 적용 및 사용할 수 있는 상태인지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad1b9-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="ad1b9-117">**완료를** 클릭하여 온라인 인증서 요청 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ad1b9-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="ad1b9-118">이 인증서를 비즈니스용 **Skype 서버** 인증서 사용에 할당 확인란을 선택한 경우 인증서가 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad1b9-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="ad1b9-119">이 확인란을 선택 취소한 경우 별도의 단계에서 인증서를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad1b9-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ad1b9-120">발급 CA(인증 기관) 루트 인증서가 컴퓨터의 신뢰할 수 있는 루트 인증 기관 저장소에 없는 경우 또는 중간 CA 인증서가 적절한 저장소에 없는 경우 다음 그림과 같이 요약 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad1b9-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="ad1b9-121">인증서를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad1b9-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="ad1b9-122">인증서 할당 프로세스를 완료하려면 발급 CA 루트 인증서 및 모든 중간 CA 인증서를 가져온 다음 기본 인증서 마법사 페이지에서 **할당** 을 클릭하여 인증서를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad1b9-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

