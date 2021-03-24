---
title: Office Web Apps Server 설정 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/19/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
description: 구성된 Office Web Apps 서버의 속성을 편집합니다. 편집 가능한 속성은 다음과 같습니다.
ms.openlocfilehash: e9f4a188c5cb58be685db4ea44157f2897ebe5ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095542"
---
# <a name="edit-office-web-apps-server-settings"></a><span data-ttu-id="26fc7-104">Office Web Apps Server 설정 편집</span><span class="sxs-lookup"><span data-stu-id="26fc7-104">Edit Office Web Apps Server Settings</span></span>

<span data-ttu-id="26fc7-105">구성된 Office Web Apps 서버의 속성을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="26fc7-105">You edit the properties of the configured Office Web Apps Server.</span></span> <span data-ttu-id="26fc7-106">편집 가능한 속성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="26fc7-106">The following properties are available to edit:</span></span>

 <span data-ttu-id="26fc7-107">**Office Web Apps 서버 FQDN:** 이 속성은 Office Web Apps 서버의 정식 도메인 이름을 정의하며 DNS(Domain Name System) 호스트 A 또는 AAAA(IPv6을 사용하는 경우) 레코드와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fc7-107">**Office Web Apps Server FQDN**: This property defines the fully qualified domain name of the Office Web Apps Server and should match a domain name system (DNS) host A or AAAA (if IPv6 is being used) record.</span></span>

 <span data-ttu-id="26fc7-108">**Office Web Apps 서버** 검색 URL: Office Web Apps 서버에 대한 클라이언트 액세스용 URL(Uniform Resource Locator)입니다. 서버가 배포에 대한 내부 네트워크가 없는 다른 네트워크 영역으로 배치된 경우 이 주소를 기본값에서 편집해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fc7-108">**Office Web Apps Server discovery URL**: The uniform resource locator (URL) for client access to the Office Web Apps Server, you may need to edit this address from its default if the server is placed in another network zone other than the internal network for your deployment.</span></span>

<span data-ttu-id="26fc7-109">이 서버가 경계 네트워크 또는 기타 네트워크 영역(경계 네트워크, 신뢰도가 낮은 네트워크 및 인터넷을 내부 배포와 구분하는 내부 방화벽 외부에 있음)에 배포되는 경우 **Office Web Apps Server를 외부 네트워크(경계/인터넷)에 배포** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26fc7-109">Select the check box **Office Web Apps Server is deployed in an external network** if this server is deployed in your perimeter network or other network zone that is outside of your internal firewall separating the perimeter network, less trusted networks, and the Internet from your internal deployment.</span></span>

![Office Web Apps 설정 확장기](../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="26fc7-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26fc7-111">See also</span></span>

[<span data-ttu-id="26fc7-112">회의의 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="26fc7-112">Components and Topologies for Conferencing</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)