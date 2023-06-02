# sidebarHASS
Homeassistant layout with the sidebar card

Required HACS Frontend Mods
  mini-graph-card
  simple-weather-card
  layout-card
  mini-media-player

Sidebar
  The sidebar is controlled from within sidebar.yaml

Pages
  All of the sidebar pages can be found inside of pages/"page"

Grid
  Some pages have a grid layout, you can add this grid to other cards with the following.
    The page should have a layout before the cards.

        layout:
      gridrows: auto
      grid-template-columns: repeat(4, 1fr) 0
      grid-template-rows: 0 repeat(2, fit-content(100%)) 0fr
      grid-template-areas: |
        "sidebar  .           .       .       ."
        "sidebar  A1          A2      A3      ."
        "sidebar  B1          B2      B3      ."
        "sidebar  footer      footer  footer  ."
    
Once the layout is added you will then use a custom:grid-layout card and place the object in the grid.
    
      - show_state: true
        show_name: true
        camera_view: auto
        type: picture-entity
        entity: camera.camera_1_camera_1
        aspect_ratio: '16:10'
        name: Camera-1
        view_layout:
          grid-area: A1

This places the camera1 entity on A1 within the grid.
 
