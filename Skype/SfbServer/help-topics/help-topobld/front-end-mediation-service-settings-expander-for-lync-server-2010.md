---
title: Lync Server 2010의 프론트 엔드 중재 서비스 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 이 대화 상자에서 중재 서버 PSTN 게이트웨이 설정의 속성을 편집 합니다. 다음 설정을 정의 합니다.
ms.openlocfilehash: b57ca675d3681886ea2a2853aa1357b394fda4c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189912"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="aeeeb-104">Lync Server 2010의 프론트 엔드 중재 서비스 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="aeeeb-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="aeeeb-105">이 대화 상자에서 **중재 서버 PSTN 게이트웨이** 설정의 속성을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="aeeeb-106">다음 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-106">You define the following settings:</span></span>
  
- <span data-ttu-id="aeeeb-107">이 프런트 엔드 서버 또는 프런트 엔드 풀을 사용 하 여 조정 서버를 collocate 하려면 **Collocated 중재 서버** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="aeeeb-108">**수신 대기 포트**: 중재 서버가 수신 대기 하는 포트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="aeeeb-109">**TLS** 또는 전송 계층 보안, **TCP**또는 전송 제어 프로토콜에 대 한 포트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="aeeeb-110">TCP에 대 한 포트 항목을 사용 하려면 **tcp 포트 사용**확인란을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="aeeeb-111">포트 값 TLS, TCP 또는 둘 다를 사용 하도록 설정 하 고 정의 해야 하는지 여부는 공용 전환 통신 네트워크 (PSTN) 게이트웨이에 대 한 설명서 및 구성 설정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="aeeeb-112">TLS는 중재 서버와 PSTN 게이트웨이 간의 트래픽을 암호화 하는 인증서를 사용 하 여 보다 안전한 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="aeeeb-113">일부 PSTN 게이트웨이가 TLS를 지원 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="aeeeb-114">현재 연결되어 있는 기존 **트렁크**, 즉 SIP(Session Initiation Protocol) 트렁크, **게이트웨이**(PSTN 게이트웨이 또는 IP-PBX), **사이트**(트렁크 및 게이트웨이용으로 구성된 사이트)의 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="aeeeb-p105">트렁크, 게이트웨이 및 사이트를 선택하고 **기본값으로 설정**을 클릭하여 선택 항목을 이 중재 서비스의 기본값으로 설정합니다. 선택 항목의 현재 기본값 설정을 제거하려면 현재 기본값을 선택하고 **기본값으로 설정 안 함**을 선택합니다. 그런 다음 새 기본값을 선택하고 **기본값으로 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="aeeeb-118">**확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="aeeeb-119">**취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="aeeeb-120">**도움말**: 이 도움말 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-120">**Help** Displays this help screen.</span></span>
  

