---
title: Office Web Apps 서버 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 새 Office Web Apps 서버 정의 마법사는 배포에 새 Office Web Apps 서버를 정의 합니다. 다음 정보를 입력 합니다.
ms.openlocfilehash: d1b36a2146d6be0addd9b66fd02665eee8de907d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187122"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="13324-104">Office Web Apps 서버 추가</span><span class="sxs-lookup"><span data-stu-id="13324-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="13324-105">**새 Office Web Apps 서버 정의** 마법사는 배포에 새 Office Web apps 서버를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="13324-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="13324-106">다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="13324-106">You fill in the following information:</span></span>

 <span data-ttu-id="13324-107">**Office Web Apps 서버 FQDN**: Office Web apps 서버를 호스팅할 서버의 정규화 된 도메인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="13324-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="13324-108">**Office Web Apps server 검색 url**: Office Web apps 서버의 전체 url (uniform resource locator)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="13324-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="13324-109">**Office Web Apps 서버 검색 URL** 의 기본 동작은 다음 `https://<FQDN of the Office Web Apps Server/hosting/discovery` 형식으로 OFFICE web apps 서버의 FQDN을 기반으로 URL을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13324-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="13324-110">대부분의 경우 기본 서식을 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13324-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="13324-111">Office Web Apps 서버와 Office Web Apps 서버 검색 URL이 달라 야 하는 경우 기본 형식을 변경 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13324-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="13324-112">예를 들어 Office Web Apps 서버는 주변 네트워크에 배치 되며 위치에 따라 다른 URL을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13324-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="13324-113">**외부 네트워크 (즉, 주변/인터넷)에 배포 된 Office Web Apps 서버**: 주변 네트워크, 외부 네트워크 또는 기타 네트워크 영역과 같은 내부 방화벽 외부에 Office Web apps 서버가 배치 된 경우 확인란을 선택 합니다. 이는 내부 네트워크와 동일 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13324-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="13324-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13324-114">See also</span></span>

[<span data-ttu-id="13324-115">회의 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="13324-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
