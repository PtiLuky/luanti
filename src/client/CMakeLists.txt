set(sound_SRCS ${CMAKE_CURRENT_SOURCE_DIR}/sound.cpp)

if(USE_SOUND)
	list(APPEND sound_SRCS
		${CMAKE_CURRENT_SOURCE_DIR}/sound/al_extensions.cpp
		${CMAKE_CURRENT_SOURCE_DIR}/sound/al_helpers.cpp
		${CMAKE_CURRENT_SOURCE_DIR}/sound/ogg_file.cpp
		${CMAKE_CURRENT_SOURCE_DIR}/sound/playing_sound.cpp
		${CMAKE_CURRENT_SOURCE_DIR}/sound/proxy_sound_manager.cpp
		${CMAKE_CURRENT_SOURCE_DIR}/sound/sound_data.cpp
		${CMAKE_CURRENT_SOURCE_DIR}/sound/sound_manager.cpp
		${CMAKE_CURRENT_SOURCE_DIR}/sound/sound_openal.cpp
		${CMAKE_CURRENT_SOURCE_DIR}/sound/sound_singleton.cpp
	)
	set(SOUND_INCLUDE_DIRS
		${OPENAL_INCLUDE_DIR}
		${VORBIS_INCLUDE_DIR}
		${OGG_INCLUDE_DIR}
		PARENT_SCOPE)
	set(SOUND_LIBRARIES
		${OPENAL_LIBRARY}
		${VORBIS_LIBRARIES}
		PARENT_SCOPE)
endif()

file(GLOB_RECURSE client_HDRS "${CMAKE_CURRENT_SOURCE_DIR}/*.h")

set(client_SRCS
	${client_HDRS}
	${sound_SRCS}
	${CMAKE_CURRENT_SOURCE_DIR}/meshgen/collector.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/render/anaglyph.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/render/core.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/render/factory.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/render/interlaced.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/render/plain.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/render/sidebyside.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/render/stereo.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/render/secondstage.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/render/pipeline.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/activeobjectmgr.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/camera.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/client.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/clientenvironment.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/clientlauncher.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/clientmap.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/clientmedia.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/clientobject.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/clouds.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/content_cao.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/content_cso.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/content_mapblock.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/filecache.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/fontengine.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/game.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/gameui.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/game_formspec.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/guiscalingfilter.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/hud.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/imagefilters.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/inputhandler.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/item_visuals_manager.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/joystick_controller.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/keycode.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/localplayer.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/mapblock_mesh.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/mesh.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/mesh_generator_thread.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/minimap.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/particles.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/renderingengine.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/shader.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/sky.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/tile.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/texturepaths.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/texturesource.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/imagesource.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/wieldmesh.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/shadows/dynamicshadows.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/shadows/dynamicshadowsrender.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/shadows/shadowsshadercallbacks.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/shadows/shadowsScreenQuad.cpp
	PARENT_SCOPE
)
