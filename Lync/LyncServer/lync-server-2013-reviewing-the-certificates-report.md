---
title: 'Lync Server 2013: 인증서 보고서 검토'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="9014e-102">Lync Server 2013에서 인증서 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="9014e-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9014e-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9014e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9014e-104">인증서 보고서에는 권장 Lync Server 2013 배포에 필요한 모든 인증서가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="9014e-105">계획 도구는 입력 된 주체 이름 및 주체 대체 이름에 대 한 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="9014e-106">편집 되지 않은 상태로 유지 되는 기본 텍스트는 인증서 요청 및 발급을 담당 하는 팀의 잠재적인 챌린지를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="9014e-107">또한 인증서 정보에는 일반적으로 인증서를 발급할 수 있는 위치에 대 한 정보도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="9014e-108">인프라에 내부 PKI (공개 키 인프라)가 없으면 공용 인증서 공급자를 통해 모든 인증서를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="9014e-109">EKU (확장 키 용도) 및 보고서의 필드에 할당은 각 인증서의 용도와 위치를 이해 하는 데 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="9014e-110">![인증서 관리 보고서](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "인증서 관리 보고서")</span><span class="sxs-lookup"><span data-stu-id="9014e-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="9014e-111">신중 하 게 검토 하 고 배포에서 각 인증서의 용도와 목적을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="9014e-112">인증서가 수행 하는 작업에 대 한 질문이 있는 경우 어떤 서버나 서비스와 통신 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="9014e-113">Lync Server 2013의 인증서는 두 가지 주요 목적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="9014e-114">MTLS (상호 전송 계층 보안) – 통신과 관련 된 컴퓨터는 각각 자신의 id를 다른 컴퓨터에 증명 하는 인증서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-114">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="9014e-115">이를 서버 인증 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-115">This is known as server authentication.</span></span> <span data-ttu-id="9014e-116">각 컴퓨터가 다른 컴퓨터의 id를 신뢰 해야 통신을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-116">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="9014e-117">암호화 – 암호화 (보안 소켓 계층 또는 SSL, 전송 계층 보안 또는 TLS)는 통신을 보호 하 고, 개인 정보 보호를 보장 하며, 신뢰할 수 있는 통신 및 공동 작업 시스템을 만들 수 있도록 하는 중요 한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9014e-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9014e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9014e-118">See Also</span></span>


[<span data-ttu-id="9014e-119">Lync Server 2013에서 관리자 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="9014e-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

