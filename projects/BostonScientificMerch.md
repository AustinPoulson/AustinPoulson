# Boston Scientific Merch <img width="250" height="36" alt="image" src="https://github.com/user-attachments/assets/1b9aa2b6-f35e-4a49-8dfb-addc66435ad5" />
*Last Updated: Aug 5th 2025*

Visit the site: [https://bostonscientificmerch.com/](https://bostonscientificmerch.com/)

### Project Overview

Boston Scientific needed a centralized platform for employees to order branded merchandise while maintaining brand integrity. As a developer at Merchology, my role was to convert their Figma design into a fully functional Shopify-powered online merch store.

### My Roles & Resposibilities

- Implementing the design into a functioning website.
- Ownership of the Shopify store.
- Consultation on the technical capabilities of the platform.
- Understanding customer use-cases and implementing custom solutions.

The project went through several iterations during the initial development phase. 

Final Implementation:

<img width="2560" height="2858" alt="screencapture-bostonscientificmerch-2025-08-04-14_04_03" src="https://github.com/user-attachments/assets/a9961aad-9ddb-440c-9ad3-9c1d7c7dd3ce" />

Design Document:

<img width="1935" height="1214" alt="image" src="https://github.com/user-attachments/assets/96ba692e-7cb4-48a0-b94d-97abb8eb1f10" />

### Challenges & Solutions

**Challenge:** Single sign-on (SSO) - This site required an SSO integration with Boston Scientifics Microsoft-based account system. Shopify doesn't natively support SSO. We also didn't have direct access to Boston Scientifics identity provider.

**Solution:** Given Shopify's lack of native support for SSO, our next best option was a third party app. We compared a few options but eventually settled on MiniOrange because of it's simple interface and compatibility with Boston Scientifics identity provider. I worked directly with the clients technical staff to implement the system. We established the connection quickly with minimal troubleshooting. We had some initial hiccups, but both teams were professional and handled the implementation skillfully. The results were better than expected. Thanks to Microsofts well built system, it supports not only Boston Scientifics sign-on system, but all Microsoft enterprise sign-ons. Now all customer accounts will be linked to the relevant Microsoft account as-well.


**Challenge:** The design document showed a specific blog post element on the homepage, but implied it should link to a product collection. The dawn theme doesn't natively support linking to collections from these blog post tiles.

**Solution:** I implemented a tagging solution to get around this. I modified the blog post element to use dynamic href assignment. When a blog post is tagged with `redirect=/some-page`, the element will swap out the link with the redirected page before serving itself to the client. This was required because of two conditions. 1. Native Shopify redirects only work if the blog post is set to `hidden`. 2. Hiding a blog post prevents that post from appearing on the homepage. It's a catch 22. That's why the custom solution was necessary.

### Results & Impact

The Boston Scientific merch store was completed and delivered fulfilling the contract and satisfying the stakeholders. The store continues to be supported by Merchologys order fulfillment team. Tech mantanence is minimal with this type of project, but I remain on call for any further technical issues (none so far).

Through this project we:
- Delivered a feature-rich Shopify store aligned closely with Boston Scientific’s brand standards.
- Moved quickly - The development portion of the project was completed in half the estimated time.
- Received positive feedback from the client.
