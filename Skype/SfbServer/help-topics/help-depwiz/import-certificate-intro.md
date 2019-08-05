---
title: 인증서 가져오기 (소개)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: 인증서를 가져오려면 인증서 파일에 대 한 경로를 제공 해야 합니다. 인증서 파일 선택 텍스트 상자에서 전체 경로와 파일 이름을 입력 하거나, 찾아보기 단추를 클릭 하 고 경로 위치와 파일 이름 (일반적으로. p7b, .pfx 또는 .cer 파일)으로 이동할 수 있습니다.
ms.openlocfilehash: b1bf46efaefb8a400158cac7ed5fd9527c7272f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186621"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="6af9a-104">인증서 가져오기 (소개)</span><span class="sxs-lookup"><span data-stu-id="6af9a-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="6af9a-105">인증서를 가져오려면 인증서 파일에 대 한 경로를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-105">To import a certificate, you must provide a path to the certificate file.</span></span> <span data-ttu-id="6af9a-106">**인증서 파일 선택** 텍스트 상자에서 전체 경로와 파일 이름을 입력 하거나, **찾아보기** 단추를 클릭 하 고 경로 위치와 파일 이름 (일반적으로. p7b, .pfx 또는 .cer 파일)으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-106">In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="6af9a-107">인증서에 개인 키가 포함 되어 있으면 인증서 **파일에 인증서의 개인 키가 포함**된 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="6af9a-108">이 확인란을 선택 하면 **암호** 텍스트 입력을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="6af9a-109">개인 키와 연결 된 인증서가 있는 경우 일반적으로 인증서가 만들어질 때 개인 키에 암호가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="6af9a-110">개인 키에 대 한 암호를 입력 하 여 인증서와 개인 키를 인증서 저장소로 가져올 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="6af9a-111">인증서 파일 경로에 대 한 정보를 제공 하 고 필요에 따라 개인 키 암호를 입력 하는 경우 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6af9a-112">개인 키에 대 한 암호를 모르는 경우에는 가져오지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

