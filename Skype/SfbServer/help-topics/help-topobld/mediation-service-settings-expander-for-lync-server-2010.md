---
title: Lync Server 2010 대한 중재 서비스 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 다음 속성을 정의하여 중재 서비스의 속성을 편집합니다.
ms.openlocfilehash: ddc6ab56f848179800b6398b7a638cdb7a061a9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806688"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="0e514-103">Lync Server 2010 대한 중재 서비스 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="0e514-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="0e514-104">다음 속성을 정의하여 중재 서비스의 속성을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="0e514-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="0e514-105">**수신 포트:** 중재 서비스에서 수신할 **TLS** 포트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e514-105">**Listening ports**: Define the **TLS** port that the Mediation service will listen on.</span></span> <span data-ttu-id="0e514-106">기본적으로 포트 값은 TLS(전송 계층 보안)를 통해 TCP 5067입니다.</span><span class="sxs-lookup"><span data-stu-id="0e514-106">By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="0e514-107">원하는 경우 **TCP 포트 값을** 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e514-107">Optionally, you define a **TCP** port value.</span></span> <span data-ttu-id="0e514-108">기본적으로 이 값은 TCP 5068입니다.</span><span class="sxs-lookup"><span data-stu-id="0e514-108">By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e514-109">TCP 포트 값 설정은 **TCP 포트 사용(Enable TCP port)을 선택하여 사용하도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="0e514-109">The TCP port value setting is enabled by selecting **Enable TCP port**.</span></span> <span data-ttu-id="0e514-110">중재 서비스와 통신하는 데 필요한 포트 설정에 대한 요구 사항은 PSTN(Public Switched Telephone Network) 게이트웨이 또는 IP-PBX(Internet Protocol Private Branch Exchange)에 대한 설명서를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e514-110">You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="0e514-111">**TCP 포트를** 사용하도록 설정하여 PSTN 게이트웨이 또는 IP-PBX의 TCP 통신에 대한 포트 값을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e514-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="0e514-112">현재 연결되어 있는 기존 **트렁크**, 즉 SIP(Session Initiation Protocol) 트렁크, **게이트웨이**(PSTN 게이트웨이 또는 IP-PBX) 및 **사이트**(트렁크 및 게이트웨이용으로 구성된 사이트)의 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e514-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="0e514-p104">트렁크, 게이트웨이 및 사이트를 선택하고 **기본값으로 설정** 을 클릭하여 선택 항목을 이 중재 서비스의 기본값으로 설정합니다. 선택 항목의 현재 기본값 설정을 제거하려면 현재 기본값을 선택하고 **기본값으로 설정 안 함** 을 선택합니다. 그런 다음 새 기본값을 선택하고 **기본값으로 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0e514-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="0e514-116">**확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="0e514-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="0e514-117">**취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0e514-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="0e514-118">**도움말**: 이 도움말 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0e514-118">**Help** Displays this help screen.</span></span>
  

